# Attacking Common Applications

> Status: 🟨 In progress

## Overview
اختبار اختراق تطبيقات/أنظمة شائعة (CMS زي WordPress, panels إدارية, tools معروفة) بالاعتماد على fingerprinting وثغراتها المعروفة (CVEs).

## Key Concepts
- أول خطوة دايمًا fingerprinting دقيق للنسخة المستخدمة
- البحث عن CVEs معروفة للنسخة المكتشفة قبل أي استغلال يدوي
- كتير من التطبيقات بتيجي بإعدادات افتراضية خطيرة (default creds, debug mode)

## Important Commands / Tools
```bash
whatweb <url>
wpscan --url <url> --enumerate vp,vt,u
searchsploit <application_name> <version>
```

## Lab Notes / Walkthrough
- اتبعت تسلسل: fingerprint → searchsploit → تأكيد الثغرة يدويًا قبل استخدام أي exploit جاهز

## Common Mistakes / Gotchas
- تشغيل exploit جاهز بدون فهم إيه اللي بيعمله فعليًا على السيرفر

## Related Cheatsheet
- [../../cheatsheet/](../../cheatsheet/)
