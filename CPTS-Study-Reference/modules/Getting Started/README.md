# Getting Started

> Status: 🟨 In progress

## Overview
أساسيات الشغل على بيئة Linux/Kali: الاتصال بالـ VPN، إدارة الـ terminal بـ tmux، والأدوات الأساسية اللي هتتكرر في كل موديول بعد كده.

## Key Concepts
- OpenVPN connection وإدارة الـ pwnbox / الجهاز المحلي
- tmux sessions عشان تقدر تشغل أكتر من حاجة بالتوازي
- أساسيات SSH, netcat, curl

## Important Commands / Tools
```bash
sudo openvpn lab_<user>.ovpn      # الاتصال بالـ VPN
ip a                               # التأكد من الـ interface الجديد (tun0)
ping -c 4 <target>
tmux new -s pentest
```

## Lab Notes / Walkthrough
- جربت أعمل split panes في tmux عشان أتابع nmap وshell في نفس الوقت
- وثقت أهم shortcuts استخدمتها يوميًا

## Common Mistakes / Gotchas
- نسيان التأكد من اتصال tun0 قبل بدء أي scan

## Related Cheatsheet
- [../../cheatsheet/](../../cheatsheet/)
