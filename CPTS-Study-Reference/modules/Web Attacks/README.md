# Web Attacks

> Status: 🟨 In progress

## Overview
هجمات ويب عامة إضافية مش مغطاة في الموديولات التانية: IDOR, CSRF, SSRF, Open Redirect — ثغرات منطق التطبيق أكتر من ثغرات تقنية بحتة.

## Key Concepts
- IDOR بيحصل لما الـ authorization check غائب حتى لو الـ authentication موجود
- CSRF بيستغل إن المتصفح بيبعت الكوكيز تلقائيًا مع أي طلب
- SSRF بيخلي السيرفر نفسه ينفذ طلب لمصدر المهاجم بيحدده

## Important Commands / Tools
```text
/api/user/1001/profile -> جرب 1002, 1003...
http://<host>/fetch?url=http://169.254.169.254/latest/meta-data/
```

## Lab Notes / Walkthrough
- أهم حاجة اتعلمتها هنا: دايمًا جرب تغيير IDs/parameters بعد تسجيل دخول بحساب عادي
- وثقت أمثلة الـ payloads في [Web-Attacks cheatsheet](../../cheatsheet/Web-Attacks.md)

## Common Mistakes / Gotchas
- الخلط بين CSRF و XSS رغم إنهم مختلفين في الآلية والدفاع

## Related Cheatsheet
- [../../cheatsheet/](../../cheatsheet/)
