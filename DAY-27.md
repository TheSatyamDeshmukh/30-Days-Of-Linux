# Day 27 🔐 — Linux Hardening & Security Best Practices

> **"Ek secure Linux server = hackers ke liye headache!"**

---

## 🛡️ Security Checklist

```
✅ System update karo
✅ Unnecessary services band karo
✅ Strong passwords
✅ SSH hardening
✅ Firewall enable karo
✅ fail2ban install karo
✅ Root login disable karo
✅ Audit logs enable karo
✅ File permissions check karo
✅ Unused users/software remove karo
```

---

## 1️⃣ System Updated Rakho

```bash
sudo apt update && sudo apt upgrade -y

# Automatic security updates:
sudo apt install unattended-upgrades
sudo dpkg-reconfigure --priority=low unattended-upgrades
```

---

## 2️⃣ Unnecessary Services Band Karo

```bash
# Running services dekho
systemctl list-units --type=service --state=running

# Unnecessary services disable karo
sudo systemctl disable bluetooth
sudo systemctl stop bluetooth
sudo systemctl disable cups       # Printing nahi chahiye server pe
sudo systemctl stop cups
```

---

## 3️⃣ SSH Hardening — Complete

```bash
sudo cp /etc/ssh/sshd_config /etc/ssh/sshd_config.bak  # Backup!
sudo nano /etc/ssh/sshd_config
```

```
# --- SSH Security Settings ---

# Root se seedha login band karo
PermitRootLogin no

# Password login band karo (keys use karo)
PasswordAuthentication no

# Empty passwords band karo
PermitEmptyPasswords no

# Port badlo (optional but helpful)
Port 2222

# Protocol version
Protocol 2

# Idle connections timeout
ClientAliveInterval 300
ClientAliveCountMax 2

# Login attempts limit
MaxAuthTries 3

# Sirf specific users allow karo
AllowUsers rahul priya

# X11 forwarding band karo (agar GUI nahi chahiye)
X11Forwarding no
```

```bash
sudo systemctl restart sshd
```

---

## 4️⃣ Firewall — UFW Setup

```bash
# Default rules — sab band karo
sudo ufw default deny incoming
sudo ufw default allow outgoing

# Sirf zaroori ports kholo
sudo ufw allow 2222/tcp     # SSH (naya port)
sudo ufw allow 80/tcp       # HTTP
sudo ufw allow 443/tcp      # HTTPS

# Enable karo
sudo ufw enable
sudo ufw status verbose
```

---

## 5️⃣ fail2ban — Brute Force Protection

```bash
sudo apt install fail2ban
sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local
sudo nano /etc/fail2ban/jail.local
```

```ini
[DEFAULT]
bantime = 3600       # 1 ghanta ban
findtime = 600       # 10 minute window
maxretry = 5         # 5 attempts

[sshd]
enabled = true
port = 2222          # Tumhara SSH port
logpath = /var/log/auth.log
```

```bash
sudo systemctl enable fail2ban
sudo systemctl start fail2ban
sudo fail2ban-client status sshd
```

---

## 6️⃣ File Permissions Audit

```bash
# World-writable files dhundho (dangerous!)
find / -type f -perm -o+w 2>/dev/null | grep -v /proc | grep -v /sys

# SUID files dhundho
find / -type f -perm /4000 2>/dev/null

# Root-owned SUID files
find / -user root -perm -4000 2>/dev/null

# /etc/passwd aur /etc/shadow permissions
ls -la /etc/passwd /etc/shadow
# passwd: -rw-r--r-- (644)
# shadow: -rw-r----- (640) ya -rw------- (600)
```

---

## 7️⃣ Users Audit

```bash
# Users jo bash shell use karte hain (real users)
grep /bin/bash /etc/passwd

# Users jinka password nahi set (!)
sudo grep "^[^:]*:!" /etc/shadow

# Inactive users lock karo
sudo passwd -l unuseduser

# Old accounts delete karo
sudo userdel -r olduser
```

---

## 8️⃣ Logs Monitor Karo

```bash
# Auth logs monitor
sudo tail -f /var/log/auth.log
sudo grep "Failed password" /var/log/auth.log

# Last logins
last
lastb                             # Failed login attempts

# Who is logged in?
who
w
```

---

## 9️⃣ Security Audit Tools

```bash
# Lynis — automatic security audit
sudo apt install lynis
sudo lynis audit system           # Poora audit karo
# Score milega aur recommendations

# chkrootkit — rootkit check
sudo apt install chkrootkit
sudo chkrootkit

# rkhunter — another rootkit hunter
sudo apt install rkhunter
sudo rkhunter --check
```

---

## 🏋️ Practice — Server Harden Karo

```bash
# 1. Update
sudo apt update && sudo apt upgrade -y

# 2. UFW setup
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow ssh
sudo ufw enable

# 3. fail2ban install
sudo apt install fail2ban
sudo systemctl enable fail2ban

# 4. Audit
sudo lynis audit system 2>/dev/null | tail -20
```

---

## 📝 Aaj Ka Summary

✅ Regular updates = Security ka base
✅ SSH: No root, no password, change port
✅ UFW: Default deny, sirf zaroori ports kholo
✅ fail2ban: Brute force automatically block
✅ Lynis: Automatic security audit
✅ Regular log review zaroori hai!

---
**Day:** 27/30 | **Topic:** Linux Hardening | **Difficulty:** ⭐⭐⭐⭐☆
