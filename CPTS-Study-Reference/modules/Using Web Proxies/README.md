# Using Web Proxies

> Status: 🟨 In progress

## Overview
استخدام Burp Suite (أو ZAP) لاعتراض وتعديل طلبات/ردود الويب أثناء اختبار تطبيقات الويب — أساس كل اختبار اختراق ويب تقريبًا.

## Key Concepts
- Proxy بيحط نفسه man-in-the-middle بين المتصفح والسيرفر
- Repeater لإعادة إرسال وتعديل طلب واحد يدويًا
- Intruder للـ automation/fuzzing على الطلب

## Important Commands / Tools
```text
Burp Proxy listener: 127.0.0.1:8080
تحميل شهادة Burp CA على المتصفح عشان HTTPS يشتغل
```
```bash
curl -x http://127.0.0.1:8080 -k http://<target>
```

## Lab Notes / Walkthrough
- ضبطت FoxyProxy على المتصفح عشان أبدّل بسهولة بين proxy شغال ومش شغال
- استخدمت Repeater كتير لتجربة SQLi/XSS payloads يدويًا قبل ما أدخل automation

## Common Mistakes / Gotchas
- نسيان تثبيت شهادة Burp CA فيبقى فيه SSL errors على كل حاجة HTTPS

## Related Cheatsheet
- [../../cheatsheet/](../../cheatsheet/)
