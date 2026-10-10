# Documentation & Reporting

> Status: 🟨 In progress

## Overview
كتابة تقرير اختبار اختراق احترافي: Executive Summary للإدارة، Technical Findings للفريق التقني، وRemediation عملي — مهارة مهمة بقد المهارات التقنية.

## Key Concepts
- كل finding لازم يكون reproducible بخطوات واضحة (PoC)
- ترتيب النتائج حسب الخطورة (CVSS) مش حسب ترتيب اكتشافها
- Executive Summary لازم يبقى مفهوم لغير التقنيين

## Important Commands / Tools
```text
CVSS Calculator لتحديد درجة كل ثغرة
Markdown / Dradis / Serpico لتنظيم التقرير
```

## Lab Notes / Walkthrough
- بنيت template ثابت بستخدمه لكل finding: Description / Impact / PoC / Remediation / CVSS
- اتعودت أوثق أول بأول وقت الاختبار مش بعد الانتهاء خالص

## Common Mistakes / Gotchas
- كتابة توصيات عامة جدًا ("حدّث النظام") بدل خطوات remediation محددة

## Related Cheatsheet
- [../../cheatsheet/](../../cheatsheet/)
