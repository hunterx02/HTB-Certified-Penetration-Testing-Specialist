# Attacking Common Services

## SMB
```bash
crackmapexec smb <IP> -u <user> -p <pass>
psexec.py <domain>/<user>:<pass>@<IP>
smbclient //<IP>/<share> -U <user>
```

## MySQL
```bash
mysql -h <IP> -u root -p
mysql -h <IP> -u root -p -e "show databases;"
```

## MSSQL
```bash
impacket-mssqlclient <user>:<pass>@<IP> -windows-auth
# داخل mssqlclient:
EXEC xp_cmdshell 'whoami';
```

## RDP
```bash
xfreerdp /u:<user> /p:<pass> /v:<IP>
rdesktop <IP> -u <user> -p <pass>
```

## WinRM
```bash
evil-winrm -i <IP> -u <user> -p <pass>
crackmapexec winrm <IP> -u <user> -p <pass>
```
