# Using the Metasploit Framework

> Status: 🟨 In progress

## Overview
استخدام Metasploit كـ framework للاستغلال وإدارة الـ sessions: msfconsole, modules, payloads, و meterpreter.

## Key Concepts
- الفرق بين exploit / auxiliary / post modules
- اختيار الـ payload المناسب (staged vs stageless)
- إدارة sessions متعددة بالتوازي

## Important Commands / Tools
```bash
msfconsole
search <service/cve>
use exploit/<path>
set RHOSTS <IP>
set LHOST <attacker_ip>
run
sessions -l
```

## Lab Notes / Walkthrough
- جربت نفس الاستغلال يدويًا بعد الـ metasploit عشان أفهم إيه اللي بيحصل فعليًا

## Common Mistakes / Gotchas
- الاعتماد الكامل على msf من غير فهم الثغرة نفسها

## Related Cheatsheet
- [../../cheatsheet/](../../cheatsheet/)
