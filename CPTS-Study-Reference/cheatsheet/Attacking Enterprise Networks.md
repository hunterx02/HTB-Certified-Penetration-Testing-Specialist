# Attacking Enterprise Networks (End-to-End)

## تسلسل عام للتمرين الشامل
```text
1. External recon + enumeration (nmap, web recon)
2. Initial foothold (web vuln / weak creds / known CVE)
3. Local enumeration + privilege escalation على أول هدف
4. Credential harvesting (hashes, cached creds, config files)
5. Pivoting للشبكة الداخلية (chisel / ssh tunnel / proxychains)
6. AD enumeration (BloodHound) وتحديد مسار لـ Domain Admin
7. Lateral movement (pass-the-hash, kerberoasting)
8. تحقيق الهدف النهائي + توثيق كل الخطوات
```

## ملاحظات شخصية
- أهم حاجة في السيناريو ده التنظيم: سجل كل IP و credential لقيته أول بأول
- ارجع للـ scope باستمرار عشان متخرجش عن الحدود المسموحة
