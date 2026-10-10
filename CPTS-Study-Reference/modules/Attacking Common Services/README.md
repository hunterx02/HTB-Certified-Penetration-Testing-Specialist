# Attacking Common Services

> Status: 🟨 In progress

## Overview
اختبار اختراق خدمات شائعة زي SMB, MySQL, MSSQL, RDP, WinRM وغيرها بعد الـ enumeration، مع التركيز على misconfigurations الشائعة واستغلالها.

## Key Concepts
- كل خدمة ليها default ports وdefault credentials محتمل تكون لسه موجودة
- الفرق بين authentication misconfig و authorization misconfig
- أهمية تجربة null/guest sessions قبل أي حاجة تانية

## Important Commands / Tools
```bash
crackmapexec smb <IP> -u <user> -p <pass>
mysql -h <IP> -u root -p
impacket-mssqlclient <user>:<pass>@<IP> -windows-auth
evil-winrm -i <IP> -u <user> -p <pass>
xfreerdp /u:<user> /p:<pass> /v:<IP>
```

## Lab Notes / Walkthrough
- جمعت كل الخدمات اللي قابلتها في [Attack Common Services cheatsheet](../../cheatsheet/Attack%20Common%20Services.md)
- لاحظت إن أكتر حاجة بتدي access سريع هي default creds على MSSQL/MySQL لو مغيرتش

## Common Mistakes / Gotchas
- نسيان --windows-auth مع mssqlclient لو الحساب domain account

## Related Cheatsheet
- [../../cheatsheet/](../../cheatsheet/)
