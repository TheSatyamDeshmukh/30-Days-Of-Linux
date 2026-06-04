# Day 24 📊 — Performance Monitoring

> **"System slow kyun hai? Aaj detective ban ke pata lagate hain!"**

---

## 🖥️ CPU Monitoring

```bash
top                               # Live CPU + processes
htop                              # Better version (install karo)
mpstat                            # CPU statistics
mpstat -P ALL 1                   # Har CPU core, 1 second interval
sar -u 1 5                        # CPU usage, 1s interval, 5 times
iostat                            # CPU + disk I/O
nproc                             # CPU cores count
lscpu                             # CPU detailed info
cat /proc/loadavg                 # Load average
uptime                            # Load average (easy)
```

**Load Average Samajhna:**
```
uptime output:  1.23  0.89  0.75
                  ↑     ↑     ↑
               1 min 5 min 15 min

1 core system mein:
- 1.00 = 100% busy (normal)
- 2.00 = 200% busy (overloaded!)
- 0.50 = 50% busy (relaxed)
```

---

## 💾 Memory Monitoring

```bash
free -h                           # RAM overview (human readable)
free -m                           # MB mein
cat /proc/meminfo                 # Detailed memory info
vmstat 1 5                        # Virtual memory stats
vmstat -s                         # Memory statistics summary
swapon --show                     # Swap info
```

---

## 💿 Disk I/O Monitoring

```bash
iostat                            # Disk I/O
iostat -x 1                       # Extended, 1 second interval
iotop                             # Kaun disk use kar raha hai? (sudo chahiye)
sudo iotop -o                     # Sirf active processes
df -h                             # Disk space
du -sh /*  2>/dev/null | sort -rh | head -10  # Badi directories
```

---

## 🌐 Network Monitoring

```bash
nethogs                           # Kaun network use kar raha hai?
iftop                             # Network bandwidth live
nload                             # Network traffic simple view
ss -s                             # Socket statistics
cat /proc/net/dev                 # Network stats raw
```

---

## 🔍 Troubleshooting — System Slow Hai?

```bash
# Step 1: Load check karo
uptime

# Step 2: CPU hogging processes
ps aux --sort=-%cpu | head -10

# Step 3: Memory hogging processes
ps aux --sort=-%mem | head -10

# Step 4: Disk space full toh nahi?
df -h

# Step 5: Kaun zyada disk use kar raha?
du -sh /* 2>/dev/null | sort -rh | head -10

# Step 6: Zombie processes?
ps aux | grep Z

# Step 7: I/O wait?
iostat -x 1 3

# Step 8: Network issue?
ping -c 3 8.8.8.8
```

---

## 🏋️ Practice

```bash
uptime
free -h
df -h
ps aux --sort=-%cpu | head -5
ps aux --sort=-%mem | head -5
cat /proc/loadavg
```

---

**Day:** 24/30 | **Topic:** Performance Monitoring | **Difficulty:** ⭐⭐⭐☆☆
