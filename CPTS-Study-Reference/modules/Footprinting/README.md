# Footprinting

> Status: 🟨 In progress

## Overview
التركيز هنا على enumeration للخدمات الشائعة بعد الـ nmap: SMB, FTP, SSH, SMTP, SNMP, NFS, RPC... كل خدمة وإزاي تجمع منها معلومات مفيدة للمرحلة اللي بعدها.

## Key Concepts
- كل خدمة ليها أدوات enumeration مخصوصة (smbclient, enum4linux, rpcclient...)
- أهمية Anonymous/Null sessions في SMB و RPC
- قراءة الـ banners بعناية كمصدر معلومات

## Important Commands / Tools
```bash
smbclient -N -L //<IP>
enum4linux -a <IP>
rpcclient -U "" -N <IP>
showmount -e <IP>
snmpwalk -c public -v1 <IP>
```

## Lab Notes / Walkthrough
- وثقت لكل خدمة checklist قصيرة بالأوامر اللي بجربها بالترتيب
- فرقت بين الخدمات اللي بتدي معلومات مباشرة (SMB shares) واللي محتاجة enumeration أعمق (SNMP OIDs)

## Common Mistakes / Gotchas
- تجاهل null session enumeration على SMB/RPC

## Related Cheatsheet
- [../../cheatsheet/](../../cheatsheet/)
