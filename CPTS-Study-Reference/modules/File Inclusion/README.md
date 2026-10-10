# File Inclusion

> Status: 🟨 In progress

## Overview
ثغرات LFI (Local File Inclusion) و RFI (Remote File Inclusion) وطرق استغلالها للوصول لملفات حساسة أو الوصول لتنفيذ كود (RCE) عن طريق log poisoning أو PHP wrappers.

## Key Concepts
- LFI بيسمح بقراءة ملفات من السيرفر نفسه
- PHP wrappers (php://filter, php://input) بتفتح باب لقراءة/تنفيذ كود
- Log poisoning بيحوّل LFI بسيط لـ RCE كامل

## Important Commands / Tools
```text
http://<host>/page.php?file=../../../../etc/passwd
php://filter/convert.base64-encode/resource=config.php
```

## Lab Notes / Walkthrough
- جربت log poisoning عن طريق User-Agent وده أول مرة أربط فيها بين LFI و RCE فعليًا
- وثقت الخطوات بالترتيب في [File Inclusion cheatsheet](../../cheatsheet/File%20Inclusions.md)

## Common Mistakes / Gotchas
- السيرفر بيحتاج معرفة مكان ملف اللوج بالظبط، لو غلط المسار الاستغلال هيفشل بصمت

## Related Cheatsheet
- [../../cheatsheet/](../../cheatsheet/)
