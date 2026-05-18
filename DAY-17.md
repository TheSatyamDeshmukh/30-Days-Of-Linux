# Day 17 🏃 — Systemd & Services

> **"Systemd = Linux ka traffic controller — sab services isi ke through chalti hain!"**

---

## 🤔 Systemd Kya Hai?

Jab Linux start hota hai, **systemd** sabse pehle chalta hai (PID 1). Woh baaki sab services start karta hai — network, SSH, web server, database — sab kuch!

**Analogy:** School mein **Principal** — wo decide karta hai kaun kaun si class (service) kab chalegi.

---

## ⚙️ systemctl — Services Control 

```bash
# Service STATUS
sudo systemctl status ssh              # SSH ka status
sudo systemctl status nginx            # nginx ka status
sudo systemctl status --all            # Sab services

# Service START/STOP/RESTART
sudo systemctl start nginx             # Start karo
sudo systemctl stop nginx              # Stop karo
sudo systemctl restart nginx           # Restart karo
sudo systemctl reload nginx            # Config reload (stop nahi karta)

# ENABLE/DISABLE (boot pe start hoga ya nahi)
sudo systemctl enable nginx            # Boot pe auto-start ON
sudo systemctl disable nginx           # Boot pe auto-start OFF
sudo systemctl enable --now nginx      # Enable + abhi start bhi karo

# CHECK
sudo systemctl is-active nginx         # active/inactive
sudo systemctl is-enabled nginx        # enabled/disabled
sudo systemctl is-failed nginx         # failed hai?
```

---

## 📋 Services List Karo

```bash
systemctl list-units --type=service            # Sab services
systemctl list-units --type=service --state=running  # Sirf running
systemctl list-units --type=service --state=failed   # Failed services
systemctl list-unit-files --type=service       # Enable/disable status
```

---

## 📜 journalctl — Logs Dekho

```bash
journalctl                             # Sab logs
journalctl -f                          # Live logs (tail -f jaisa!)
journalctl -n 50                       # Aakhri 50 lines
journalctl -u nginx                    # Sirf nginx ke logs
journalctl -u nginx -f                 # nginx ke live logs
journalctl --since "1 hour ago"        # Last 1 ghante ke logs
journalctl --since "2024-01-15 10:00"  # Specific time se
journalctl -p err                      # Sirf errors
journalctl -p err -u ssh               # SSH ke errors
journalctl --disk-usage                # Logs kitni jagah le rahe hain?
sudo journalctl --vacuum-size=100M     # Logs 100MB tak rakhho, baki delete
```

---

## 🔧 Apni Khud Ki Service Banana

```bash
sudo nano /etc/systemd/system/myapp.service
```

```ini
[Unit]
Description=Meri Apni Application
After=network.target

[Service]
Type=simple
User=rahul
WorkingDirectory=/home/rahul/myapp
ExecStart=/home/rahul/myapp/start.sh
Restart=on-failure
RestartSec=5

[Install]
WantedBy=multi-user.target
```

```bash
# Service reload karo (naya file detect karo)
sudo systemctl daemon-reload

# Enable aur start karo
sudo systemctl enable myapp
sudo systemctl start myapp
sudo systemctl status myapp
```

---

## 🔄 Boot Targets (Runlevels)

```bash
systemctl get-default                  # Current target (mode)
sudo systemctl set-default graphical   # GUI mode
sudo systemctl set-default multi-user  # Text-only mode (servers ke liye)
sudo systemctl isolate rescue          # Rescue mode (emergency)
```

---

## ⏱️ Boot Time Analysis

```bash
systemd-analyze                        # Total boot time
systemd-analyze blame                  # Kaun si service zyada time le rahi?
systemd-analyze critical-chain         # Critical path
```

---

## 🏋️ Practice

```bash
# Step 1: SSH service check karo
sudo systemctl status ssh

# Step 2: Restart karo
sudo systemctl restart ssh

# Step 3: Logs dekho
journalctl -u ssh -n 20

# Step 4: Installed services dekho
systemctl list-units --type=service --state=running

# Step 5: Boot time dekho
systemd-analyze
systemd-analyze blame | head -10
```

---

## 📝 Aaj Ka Summary

✅ Systemd = Linux ka main init system (PID 1)
✅ `systemctl start/stop/restart` — service control
✅ `systemctl enable/disable` — boot pe auto-start
✅ `systemctl status` — service ki halat
✅ `journalctl -u service` — logs dekho
✅ `journalctl -f` — live logs
✅ Apni service bana sakte ho `.service` file se

---
**Day:** 17/30 | **Topic:** Systemd & Services | **Difficulty:** ⭐⭐⭐☆☆
