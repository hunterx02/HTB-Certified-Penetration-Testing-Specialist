# Attacking Web Applications with ffuf

## Directory / File / Extension
```bash
ffuf -w <wordlist>:FUZZ -u http://<IP>:<PORT>/FUZZ
ffuf -w <wordlist>:FUZZ -u http://<IP>:<PORT>/indexFUZZ        # extensions
ffuf -w <wordlist>:FUZZ -u http://<IP>:<PORT>/FUZZ -e .php,.html,.txt
ffuf -w <wordlist>:FUZZ -u http://<IP>:<PORT>/FUZZ -recursion -recursion-depth 1 -e .php
```

## Subdomains / VHosts
```bash
ffuf -w <wordlist>:FUZZ -u http://FUZZ.<domain>/
ffuf -w <wordlist>:FUZZ -u http://<IP>:<PORT>/ -H 'Host: FUZZ.<domain>' -fs <size>
```

## Parameters
```bash
ffuf -w <wordlist>:FUZZ -u http://<host>/page.php?FUZZ=key -fs <size>              # GET
ffuf -w <wordlist>:FUZZ -u http://<host>/page.php -X POST -d 'FUZZ=key' \
     -H 'Content-Type: application/x-www-form-urlencoded' -fs <size>               # POST
ffuf -w ids.txt:FUZZ -u http://<host>/page.php -X POST -d 'id=FUZZ' \
     -H 'Content-Type: application/x-www-form-urlencoded' -fs <size>               # values
```

## Filters & Tuning
```text
-fs <size>  filter size      -fc <code>  filter status     -fw <n> filter words
-fl <n>     filter lines     -mc <code>  match status      -ms <size> match size
-t <threads>   -p <delay>   -rate <n>   -o out.json -of json
```
Useful lists: `SecLists/Discovery/Web-Content/`, `SecLists/Discovery/DNS/`.
