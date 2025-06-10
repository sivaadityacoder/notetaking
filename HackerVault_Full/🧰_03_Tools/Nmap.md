# Nmap Tool

## 🔧 Common Commands
```bash
nmap -sC -sV -oN scan.txt <IP>
nmap -A -p- <IP>
nmap -Pn -T4 -p80,443 <IP>
```

## 💡 Tips
- Use `-p-` to scan all ports.
- `-sV` to detect versions.
- Combine with `gobuster` for web discovery.

## 🧪 Sample Output
```
PORT     STATE SERVICE VERSION
80/tcp   open  http    Apache httpd 2.4.29
2222/tcp open  ssh     OpenSSH 7.4
```
