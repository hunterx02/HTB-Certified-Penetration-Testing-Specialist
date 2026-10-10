# SQL Injection Fundamentals

> Status: 🟨 In progress

## Overview
أساسيات SQL Injection: اكتشافه يدويًا من غير أدوات، union-based، error-based، و blind SQLi (boolean & time-based).

## Key Concepts
- أي input بيتحط جوه query من غير sanitization ممكن يكون عرضة لـ SQLi
- Union-based بيحتاج تعرف عدد الأعمدة الأول (ORDER BY)
- Blind SQLi بتعتمد على ملاحظة فرق في السلوك مش في الرد نفسه

## Important Commands / Tools
```sql
id=1' ORDER BY 3--  -
' UNION SELECT NULL,username,password FROM users--  -
' AND SLEEP(5)--  -
' AND extractvalue(1,concat(0x7e,(SELECT version())))--  -
```

## Lab Notes / Walkthrough
- طبقت كل نوع يدويًا على الـ labs قبل ما أستخدم sqlmap عشان أفهم الفرق
- وثقت payloads الاكتشاف في [SQL Injection Fundamentals cheatsheet](../../cheatsheet/SQL%20Injection%20Fundamentals.md)

## Common Mistakes / Gotchas
- نسيان comment syntax المناسب (-- - مع مسافة، أو #) حسب نوع قاعدة البيانات

## Related Cheatsheet
- [../../cheatsheet/](../../cheatsheet/)
