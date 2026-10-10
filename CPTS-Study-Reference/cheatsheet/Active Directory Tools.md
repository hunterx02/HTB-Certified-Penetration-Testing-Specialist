# Active Directory Tools (مرجع سريع)

| الأداة | الاستخدام |
|---|---|
| `crackmapexec` / `nxc` | enumeration شامل + تنفيذ أوامر عبر SMB/WinRM |
| `bloodhound-python` + BloodHound GUI | رسم علاقات الصلاحيات داخل الدومين |
| `impacket` suite | GetUserSPNs, GetNPUsers, secretsdump, psexec, wmiexec |
| `evil-winrm` | الدخول عبر WinRM |
| `rubeus` (على Windows) | التعامل مع Kerberos tickets |
| `ldapsearch` | استعلامات LDAP يدوية |

```bash
ldapsearch -x -H ldap://<dc_ip> -D "<user>@<domain>" -w <pass> -b "DC=<domain>,DC=<tld>"
```
