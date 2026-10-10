# Login Brute Forcing

> Status: 🟨 In progress

## Overview
هجمات brute force على نماذج تسجيل الدخول في الويب والخدمات المختلفة، مع مراعاة الـ rate limiting وlockout policies عشان ميحصلش DoS غير مقصود.

## Key Concepts
- لازم تعرف شكل رسالة الخطأ (failure string) عشان الأداة تفرق بين نجاح وفشل
- بعض النماذج فيها CSRF token لازم تتعامل معاه قبل الـ brute force
- online attacks أبطأ وأخطر (lockout) من offline cracking

## Important Commands / Tools
```bash
hydra -l admin -P rockyou.txt <IP> http-post-form \
  "/login.php:username=^USER^&password=^PASS^:F=Invalid credentials"
ffuf -w rockyou.txt:FUZZ -u http://<host>/login.php -X POST \
  -d "username=admin&password=FUZZ" -fc 200 -mc 302
```

## Lab Notes / Walkthrough
- استخدمت Burp الأول لأعرف شكل الرد الناجح والفاشل بالظبط قبل ما أشغل hydra
- جربت ffuf بديل لـ hydra لما كان فيه CSRF token محتاج أعالجه في نفس الطلب

## Common Mistakes / Gotchas
- عدم تحديد failure string صح فيخلي كل المحاولات تظهر "ناجحة" غلط

## Related Cheatsheet
- [../../cheatsheet/](../../cheatsheet/)
