# Footprinting

## SMB
```bash
smbclient -N -L //<IP>
smbclient //<IP>/<share> -N
smbmap -H <IP>
enum4linux -a <IP>
crackmapexec smb <IP> -u '' -p '' --shares
```

## FTP
```bash
ftp <IP>              # جرب anonymous:anonymous
nmap --script ftp-anon -p 21 <IP>
```

## SSH
```bash
ssh -v user@<IP>       # معرفة النسخة
nmap --script ssh2-enum-algos -p 22 <IP>
```

## SMTP
```bash
nc -nv <IP> 25
VRFY root
nmap --script smtp-enum-users -p 25 <IP>
```

## SNMP
```bash
snmpwalk -c public -v1 <IP>
onesixtyone -c community.txt <IP>
```

## RPC / NFS
```bash
rpcclient -U "" -N <IP>
showmount -e <IP>
```
