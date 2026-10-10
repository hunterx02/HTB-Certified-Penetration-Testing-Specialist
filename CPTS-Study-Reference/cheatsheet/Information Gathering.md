# Information Gathering – Web Edition

## DNS
```bash
whois <domain>
dig <domain> A / MX / NS / TXT / ANY
dig @<dns_server> <domain>
dig axfr <domain> @<dns_server>      # zone transfer attempt
nslookup <domain>
host <domain>
```

## Subdomains & VHosts
```bash
subfinder -d <domain>
amass enum -passive -d <domain>
gobuster dns -d <domain> -w <wordlist>
gobuster vhost -u http://<IP> -w <wordlist> --append-domain
```
Certificate transparency: `crt.sh/?q=%25.<domain>`

## Fingerprinting
```bash
curl -I <url>
whatweb <url>
wafw00f <url>
nikto -h <url>
```

## Crawling / Content Discovery
```bash
gobuster dir -u <url> -w <wordlist> -x php,txt,html
feroxbuster -u <url> -w <wordlist>
curl <url>/robots.txt ; curl <url>/sitemap.xml
```
Also check: `/.well-known/`, Wayback Machine, Google dorks (`site:`, `inurl:`, `filetype:`).
