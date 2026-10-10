# Cross-Site Scripting (XSS)

> Status: 🟨 In progress

## Overview
أنواع XSS الثلاثة (reflected, stored, DOM-based)، طرق اكتشافها، واستغلالها بشكل تعليمي (زي سرقة cookies) في بيئة مصرّح باختبارها.

## Key Concepts
- Reflected: الـ payload بيترجع فورًا من query param
- Stored: بيتخزن في الداتابيز ويتنفذ لكل زائر للصفحة
- DOM-based: المشكلة في الـ JS client-side مش في السيرفر

## Important Commands / Tools
```html
<script>alert(1)</script>
<img src=x onerror=alert(1)>
<svg onload=alert(1)>
```

## Lab Notes / Walkthrough
- جربت bypass بسيط لفلاتر بترفض <script> باستخدام <img onerror=...>
- فرقت بين الحالات اللي الـ payload بيتنفذ فيها فورًا وبين اللي محتاجة تفاعل مستخدم تاني

## Common Mistakes / Gotchas
- اختبار XSS على نفس المتصفح بدون new tab/incognito ممكن يلخبط النتيجة بسبب caching

## Related Cheatsheet
- [../../cheatsheet/](../../cheatsheet/)
