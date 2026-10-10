# Password Attacks

> Status: 🟨 In progress

## Overview
هجمات كلمات المرور: brute force, dictionary attacks, credential stuffing, و password cracking offline بعد الحصول على hashes.

## Key Concepts
- الفرق بين online brute force وoffline cracking
- أهمية rate-limiting awareness عشان متتسببش في lockout
- اختيار الـ wordlist المناسب للسياق

## Important Commands / Tools
```bash
hydra -l <user> -P <wordlist> ssh://<IP>
hashcat -m <mode> hash.txt <wordlist>
john --wordlist=<wordlist> hash.txt
crackmapexec smb <IP> -u users.txt -p passwords.txt
```

## Lab Notes / Walkthrough
- وثقت الـ hash modes الشائعة في hashcat اللي بستخدمها كتير (NTLM, SHA256...)

## Common Mistakes / Gotchas
- تجربة brute force على خدمة production بدون إذن صريح

## Related Cheatsheet
- [../../cheatsheet/](../../cheatsheet/)
