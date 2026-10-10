# Using Web Proxies (Burp Suite / ZAP)

## Setup
```text
Proxy > Options > تأكد إن listener شغال على 127.0.0.1:8080
اضبط متصفحك / FoxyProxy على نفس البورت
نزّل شهادة Burp CA عشان HTTPS: http://burp
```

## Workflow أساسي
```text
Proxy > Intercept > اعترض الطلب
Send to Repeater (Ctrl+R) للتعديل والتكرار اليدوي
Send to Intruder (Ctrl+I) للـ fuzzing/brute-force
```

## Intruder attack types
- Sniper: متغير واحد
- Battering ram: نفس القيمة في كل المواضع
- Pitchfork: قوائم متوازية
- Cluster bomb: كل تركيبة ممكنة

## من CLI مع curl عبر الـ proxy
```bash
curl -x http://127.0.0.1:8080 -k http://<target>
```
