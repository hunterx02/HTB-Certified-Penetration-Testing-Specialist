# Attacking Enterprise Networks

> Status: 🟨 In progress

## Overview
محاكاة اختبار اختراق لشبكة مؤسسية كاملة بدمج كل المهارات السابقة end-to-end: من الـ external recon لحد الوصول لـ Domain Admin.

## Key Concepts
- التنظيم أهم من السرعة في سيناريو بهذا الحجم
- كل foothold جديد بيفتح معلومات تخدم الخطوة اللي بعدها (credentials, network maps)
- الرجوع للـ scope باستمرار عشان متخرجش عن الحدود المسموحة

## Important Commands / Tools
```text
1. External recon + enumeration (nmap, web recon)
2. Initial foothold (web vuln / weak creds / known CVE)
3. Local privilege escalation
4. Credential harvesting
5. Pivoting (chisel / ssh tunnel / proxychains)
6. AD enumeration (BloodHound) + lateral movement
7. توثيق كل خطوة
```

## Lab Notes / Walkthrough
- سجلت كل IP وcredential لقيته في ملف واحد منظم أول بأول
- رسمت خريطة بسيطة للشبكة بعد كل pivot جديد

## Common Mistakes / Gotchas
- فقدان تتبع الـ credentials/hosts بسبب عدم التوثيق أول بأول في سيناريو طويل

## Related Cheatsheet
- [../../cheatsheet/](../../cheatsheet/)
