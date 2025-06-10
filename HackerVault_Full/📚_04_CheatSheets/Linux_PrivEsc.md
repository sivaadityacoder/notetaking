# Linux PrivEsc Cheat Sheet

## 🔍 Enumeration
```bash
whoami
hostname
sudo -l
find / -perm -4000 2>/dev/null
```

## 🧠 Techniques
- **SUID**: Check for unusual SUID binaries like `find`, `nmap`, `bash`.
- **Writable /etc/passwd**: Add user with root privileges.
- **Cron jobs**: Look for scheduled scripts owned by root.

## 🛠 Tools
- linpeas.sh
- pspy
- lse.sh
