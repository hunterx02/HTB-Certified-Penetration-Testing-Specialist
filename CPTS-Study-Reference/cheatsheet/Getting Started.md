# Getting Started

## Connectivity & Basics
```bash
ifconfig / ip a                 # interfaces & IPs
ping -c 4 <target>              # reachability
sudo openvpn <file>.ovpn        # connect to lab VPN
ssh user@<IP>                   # SSH
ssh -i key.pem user@<IP>        # SSH with key
nc -nv <IP> <PORT>              # banner grab / manual connect
curl -I http://<IP>             # response headers
wget http://<IP>/file           # download
```

## tmux
```text
tmux                  # new session
Ctrl+b  c             # new window
Ctrl+b  %  /  "       # split vertical / horizontal
Ctrl+b  arrows        # move between panes
Ctrl+b  d             # detach     |  tmux attach  # re-attach
```

## Service Scanning quick start
```bash
nmap -sV -sC -p- <IP>
smbclient -N -L //<IP>
smbclient //<IP>/<share> -U <user>
ftp <IP>                         # try anonymous login
```

## Web quick start
```bash
whatweb http://<IP>
gobuster dir -u http://<IP> -w /usr/share/seclists/Discovery/Web-Content/common.txt
curl http://<IP>/robots.txt
```
