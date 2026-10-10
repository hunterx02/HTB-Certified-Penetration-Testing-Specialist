# Information Gathering - Web Edition

> Status: 🟨 In progress

## Overview
جمع المعلومات عن تطبيقات الويب والـ domains قبل الفحص النشط: DNS, subdomains, WHOIS, fingerprinting, وتحليل الـ source/headers.

## Key Concepts
- Passive recon الأول قبل أي active scanning
- أهمية certificate transparency logs لاكتشاف subdomains
- فهم الفرق بين vhost و subdomain enumeration

## Important Commands / Tools
```bash
whois <domain>
dig any <domain>
subfinder -d <domain>
gobuster vhost -u http://<IP> -w <wordlist> --append-domain
whatweb <url>
```

## Lab Notes / Walkthrough
- بنيت روتين ثابت: whois → dig → subfinder → httpx للتأكد من اللي شغال → gobuster للمحتوى

## Common Mistakes / Gotchas
- نسيان إضافة الـ domain لـ /etc/hosts بعد اكتشاف vhost جديد

## Related Cheatsheet
- [../../cheatsheet/](../../cheatsheet/)
