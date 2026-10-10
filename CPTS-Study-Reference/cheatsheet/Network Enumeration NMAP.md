# Network Enumeration – Nmap

## Host Discovery
```bash
nmap -sn <CIDR>                      # ping sweep (no port scan)
nmap -sn -iL hosts.txt               # from list
nmap -Pn <IP>                        # skip discovery (host blocks ICMP)
```

## Port Scanning
```bash
nmap <IP>                            # top 1000 TCP
nmap -p- <IP>                        # all 65535 TCP
nmap -p 22,80,443 <IP>               # specific ports
nmap --top-ports 100 <IP>
sudo nmap -sU --top-ports 50 <IP>    # UDP
nmap -sS <IP>                        # SYN scan (needs root)
nmap -sT <IP>                        # TCP connect
```

## Service / OS / Scripts
```bash
nmap -sV <IP>                        # service versions
nmap -sC <IP>                        # default scripts
nmap -sV -sC -p- <IP>                # common full combo
nmap -O <IP>                         # OS detection
nmap -A <IP>                         # aggressive (-sV -sC -O --traceroute)
nmap --script <name> -p <port> <IP>
nmap --script-help <name>
```

## Speed & Output
```bash
nmap -T4 <IP>                        # timing 0-5
nmap --min-rate 1000 <IP>
nmap -oN scan.txt -oX scan.xml -oG scan.gnmap <IP>
nmap -oA scan <IP>                   # all formats
nmap -v / -vv / --reason / --packet-trace
```

## Firewall / IDS Evasion (authorized tests only)
```bash
nmap -f <IP>                         # fragment packets
nmap -D RND:5 <IP>                   # decoys
nmap -S <spoof_ip> -e <iface> <IP>
nmap --source-port 53 <IP>
```
