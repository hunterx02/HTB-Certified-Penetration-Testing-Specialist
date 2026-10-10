# Documentation & Reporting

## هيكل التقرير الأساسي
```text
1. Executive Summary          -> للإدارة، بدون تفاصيل تقنية
2. Scope & Methodology        -> إيه اللي اتفحص وإزاي
3. Findings                   -> لكل ثغرة: الوصف، الخطورة (CVSS)، إثبات (PoC), التأثير
4. Remediation                -> توصيات عملية للإصلاح
5. Appendix                   -> logs, screenshots, raw output
```

## نصائح عملية
- وثّق كل خطوة وقت ما بتحصل، مش بعد الانتهاء من كل حاجة
- كل finding لازم يبقى reproducible بخطوات واضحة
- رتب النتائج حسب الخطورة (Critical > High > Medium > Low > Info)

## أدوات
```text
CVSS Calculator لتحديد الدرجة
Markdown/LaTeX أو أدوات زي Dradis / Serpico لتنظيم التقرير
```
