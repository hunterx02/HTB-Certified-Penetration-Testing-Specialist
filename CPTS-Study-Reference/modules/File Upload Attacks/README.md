# File Upload Attacks

> Status: 🟨 In progress

## Overview
تجاوز قيود رفع الملفات (extension filtering, content-type checks) للوصول لرفع web shell وتنفيذ كود على السيرفر.

## Key Concepts
- فحص الامتداد وحده مش كافي؛ السيرفر لازم يتحقق من المحتوى الفعلي
- magic bytes ممكن تخلي ملف خبيث "يشبه" صورة
- double extension بيستغل سيرفرات بتشيك آخر امتداد بس

## Important Commands / Tools
```text
shell.php -> shell.phtml / shell.pHp5 / shell.php.jpg
GIF89a; <?php system($_GET['cmd']); ?>
```

## Lab Notes / Walkthrough
- استخدمت Burp لتعديل Content-Type وقت الرفع بدل ما أعتمد على اسم الملف بس
- بعد نجاح الرفع جربت الوصول المباشر للملف وتنفيذ أمر عن طريق ?cmd=

## Common Mistakes / Gotchas
- نسيان التحقق من مكان تخزين الملف المرفوع (ممكن يبقى خارج web root فمش هينفذ)

## Related Cheatsheet
- [../../cheatsheet/](../../cheatsheet/)
