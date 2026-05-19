# Day 18 🛡️ — Firewall & Security

> **"Firewall = Computer ka darwaan — kaun andar aayega, kaun nahi!"**


## 🔥 UFW — Uncomplicated Firewall (Ubuntu)

```bash
# UFW install aur enable karo
sudo apt install ufw
sudo ufw enable               # Firewall ON karo
sudo ufw disable              # Firewall OFF karo
sudo ufw status               # Status dekho
sudo ufw status verbose       # Detail mein
sudo ufw status numbered      # Number ke saath (delete ke liye)
```


## 📋 Rules Add Karo

```bash
# Port ALLOW karo
sudo ufw allow 22              # SSH allow karo
sudo ufw allow 80              # HTTP allow karo
sudo ufw allow 443             # HTTPS allow karo
sudo ufw allow 8080            # Custom port

# Service naam se allow karo
sudo ufw allow ssh
sudo ufw allow http
sudo ufw allow https
sudo ufw allow 'Nginx Full'    # HTTP + HTTPS dono

# Specific IP se traffic allow karo
sudo ufw allow from 192.168.1.100
sudo ufw allow from 192.168.1.0/24 to any port 22

# Port DENY karo
sudo ufw deny 23               # Telnet band karo
sudo ufw deny 3306             # MySQL band karo (internet se)
```


## ❌ Rules Delete Karo

```bash
sudo ufw status numbered       # Number dekho
sudo ufw delete 3              # Rule number 3 delete karo
sudo ufw delete allow 80       # Specific rule delete karo
sudo ufw reset                 # Sab rules reset karo (dhyan se!)
```


## 🔧 iptables — Advanced (Low Level)

```bash
sudo iptables -L               # Sab rules list karo
sudo iptables -L -n -v         # Detail mein
sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT    # Port 80 allow
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT    # SSH allow
sudo iptables -A INPUT -j DROP                         # Baaki sab drop
sudo iptables-save > /etc/iptables/rules.v4            # Rules save karo
```


## 🔐 SSH Hardening

```bash
sudo nano /etc/ssh/sshd_config
```

**Yeh settings karo:**
```
# Root login band karo
PermitRootLogin no

# Password login band karo (keys use karo)
PasswordAuthentication no

# Sirf specific users ko allow karo
AllowUsers rahul priya

# Port badlo (default 22 se)
Port 2222

# Idle timeout set karo
ClientAliveInterval 300
ClientAliveCountMax 2

# Max login attempts
MaxAuthTries 3
```

```bash
sudo systemctl restart sshd    # Changes apply karo
```


## 🔒 fail2ban — Brute Force Se Bachao

```bash
sudo apt install fail2ban
sudo systemctl enable fail2ban
sudo systemctl start fail2ban

# Config
sudo nano /etc/fail2ban/jail.local
```

```ini
[sshd]
enabled = true
port = ssh
maxretry = 3
bantime = 3600
findtime = 600
```

```bash
sudo fail2ban-client status         # Status dekho
sudo fail2ban-client status sshd    # SSH jail status
sudo fail2ban-client set sshd unbanip 1.2.3.4  # IP unban karo
```


## 🏋️ Practice

```bash
sudo ufw status
sudo ufw allow 22
sudo ufw allow 80
sudo ufw enable
sudo ufw status verbose
```


**Day:** 18/30 | **Topic:** Firewall & Security | **Difficulty:** ⭐⭐⭐⭐☆


# Day 19 📋 — Log Management

> **"Logs = Computer ki diary — kya hua, kab hua, kyun hua!"**


## 📁 Important Log Files

```bash
# Sab logs yahan hain:
ls /var/log/

# Most Important:
/var/log/syslog          # General system logs (Ubuntu)
/var/log/messages        # General logs (CentOS)
/var/log/auth.log        # Login aur authentication logs
/var/log/kern.log        # Kernel logs
/var/log/dmesg           # Boot messages
/var/log/apt/            # Package installation logs
/var/log/nginx/          # Nginx web server logs
/var/log/mysql/          # MySQL logs
```


## 🔍 Logs Padhna

```bash
cat /var/log/syslog                   # Poora log (bahut lamba!)
tail /var/log/syslog                  # Aakhri 10 lines
tail -n 50 /var/log/syslog            # Aakhri 50 lines
tail -f /var/log/syslog               # LIVE logs (Ctrl+C se rok)
head /var/log/syslog                  # Pehli 10 lines
less /var/log/syslog                  # Page by page padho
```


## 🔎 Logs Mein Dhundhna

```bash
grep "error" /var/log/syslog                    # Errors dhundho
grep -i "failed" /var/log/auth.log              # Failed logins
grep "$(date +%b\ %d)" /var/log/syslog          # Aaj ke logs
grep "Jan 15" /var/log/syslog                   # Specific date
tail -f /var/log/syslog | grep -i "error"       # Live error monitoring

# Multiple files mein dhundho
grep -r "error" /var/log/                       # Sab log folders mein
```


## 📊 journalctl — systemd Logs

```bash
journalctl                            # Sab systemd logs
journalctl -f                         # Live logs
journalctl -n 100                     # Aakhri 100 lines
journalctl --since today              # Aaj ke
journalctl --since "2024-01-15"       # Date se
journalctl --since "1 hour ago"       # Last hour
journalctl -u nginx                   # Nginx ke logs
journalctl -u ssh -f                  # SSH live logs
journalctl -p err                     # Sirf errors
journalctl -p warning                 # Warnings aur upar
journalctl -b                         # Is boot ke logs
journalctl -b -1                      # Pichle boot ke logs
```

**Priority Levels:**
```
0 = emerg    (emergency)
1 = alert
2 = crit     (critical)
3 = err      (error)
4 = warning
5 = notice
6 = info
7 = debug
```


## 🔄 Log Rotation

Logs zyada bade na ho jaayein isliye **logrotate** automatically purane logs compress karta hai.

```bash
cat /etc/logrotate.conf           # Main config
ls /etc/logrotate.d/              # App-specific configs
cat /etc/logrotate.d/nginx        # Nginx ka config

sudo logrotate -f /etc/logrotate.conf   # Force rotate
sudo logrotate -d /etc/logrotate.conf   # Debug (dry run)
```

**Custom logrotate config:**
```
/home/rahul/myapp/*.log {
    daily
    rotate 7
    compress
    missingok
    notifempty
    dateext
}
```


## 🏋️ Practice

```bash
# Auth log mein failed logins dekho
sudo grep "Failed" /var/log/auth.log | tail -20

# Live system logs
sudo tail -f /var/log/syslog

# Aaj ke errors
journalctl --since today -p err

# Disk logs kitna le rahe hain
du -sh /var/log/
journalctl --disk-usage
```


**Day:** 19/30 | **Topic:** Log Management | **Difficulty:** ⭐⭐⭐☆☆


# Day 20 🌿 — Environment Variables

> **"Environment variables = Linux ki secret settings!"**


## 🤔 Environment Variable Kya Hota Hai?

System ki **global settings** jo sab programs use karte hain. Jaise:
- `PATH` = Commands kahan se dhundhe jaayein?
- `HOME` = Tumhara home folder kahan hai?
- `USER` = Tumhara username kya hai?


## 👁️ Variables Dekhna

```bash
env                          # Sab environment variables
printenv                     # Same as env
printenv PATH                # Specific variable dekho
echo $PATH                   # $ se bhi dekh sakte ho
echo $HOME
echo $USER
echo $SHELL
echo $LANG
echo $PWD
```


## 📌 Important Variables

| Variable | Kya Hai |
|----------|---------|
| `PATH` | Directories jahan commands dhundhe jaate hain |
| `HOME` | Tumhara home directory |
| `USER` | Tumhara username |
| `SHELL` | Kaun sa shell use ho raha hai |
| `LANG` | Language setting |
| `EDITOR` | Default text editor |
| `TERM` | Terminal type |
| `PS1` | Terminal prompt ka format |


## ✏️ Variables Set Karna

```bash
# Temporary (sirf current session):
export MY_VAR="Hello Linux"
echo $MY_VAR

# Program ke liye temporary:
MY_VAR="test" python3 script.py

# Permanent banana:
nano ~/.bashrc
# Yeh line add karo:
export MY_VAR="Hello Linux"
export PATH="$PATH:/home/rahul/scripts"

# Changes apply karo:
source ~/.bashrc
# ya
. ~/.bashrc
```


## 🗂️ Config Files

```bash
~/.bashrc          # Har bash session pe run hota hai (interactive)
~/.bash_profile    # Login shell pe run hota hai
~/.profile         # Bash aur doosre shells ke liye
/etc/environment   # System-wide variables (sab users ke liye)
/etc/profile       # System-wide shell config
/etc/profile.d/    # Additional system configs
```

**Order:**
```
System boots → /etc/environment → /etc/profile → ~/.bash_profile → ~/.bashrc
```


## 🛣️ PATH — Bahut Zaroori!

```bash
echo $PATH
# /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

# PATH mein naya folder add karo:
export PATH="$PATH:/home/rahul/myscripts"

# Permanent add karo (bashrc mein):
echo 'export PATH="$PATH:/home/rahul/myscripts"' >> ~/.bashrc
source ~/.bashrc
```


## 🎨 PS1 — Prompt Customize Karo

```bash
# Default prompt change karo
echo $PS1

# Custom prompt:
export PS1="\u@\h:\w$ "
# \u = username, \h = hostname, \w = current directory

# Colored prompt:
export PS1="\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ "
```


## 🏋️ Practice

```bash
# Sab variables dekho
env | sort

# Important ones:
echo "User: $USER"
echo "Home: $HOME"
echo "Shell: $SHELL"
echo "Path: $PATH"

# Custom variable banao
export MY_NAME="Linux Learner"
echo "Hello $MY_NAME"

# .bashrc mein permanently add karo
echo 'export MY_NAME="Linux Learner"' >> ~/.bashrc
source ~/.bashrc
echo $MY_NAME
```


## 📝 Aaj Ka Summary

✅ Environment variables = System ki global settings
✅ `env` / `printenv` — sab variables dekho
✅ `export VAR="value"` — variable set karo
✅ `~/.bashrc` — permanent changes yahan likho
✅ `PATH` — commands yahan se dhundhe jaate hain
✅ `source ~/.bashrc` — changes apply karo

