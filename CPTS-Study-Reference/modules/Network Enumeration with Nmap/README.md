# Network Enumeration with Nmap

> Status: 🟨 In progress

## Overview
موديول مركّز على nmap كأداة enumeration أساسية: host discovery, port scanning, service/version detection, NSE scripts، وإزاي تبني scan strategy بدل ما تضرب -A على طول.

## Key Concepts
- الفرق بين TCP connect scan و SYN scan وتأثير الصلاحيات
- اختيار الـ timing template المناسب حسب حساسية الشبكة
- استخدام NSE scripts بدل الاعتماد على default فقط

## Important Commands / Tools
```bash
nmap -sn <CIDR>
nmap -p- --min-rate 1000 -T4 <IP>
nmap -sV -sC -p <ports> <IP>
nmap --script vuln -p <port> <IP>
```

## Lab Notes / Walkthrough
- اتبعت استراتيجية: full port scan سريع الأول، بعدين -sV -sC على الـ ports المفتوحة بس
- قارنت نتائج -T4 مع -T2 على شبكة فيها IDS

## Common Mistakes / Gotchas
- الاعتماد على top-1000 ports فقط والخدمة تكون شغالة على port غريب

## Related Cheatsheet
- [../../cheatsheet/](../../cheatsheet/)
