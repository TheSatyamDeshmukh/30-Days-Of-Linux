# Day 16 ⏰ — Cron Jobs & Automation

> **"Cron = Tumhara personal robot jo raat ko bhi kaam karta rehta hai!"**

---

## 🤔 Cron Kya Hota Hai?

Cron ek **task scheduler** hai — tum ek baar set karo, woh task automatically chalata rehta hai — daily, weekly, monthly, ya jab bhi chaho!

**Real Life Examples:**
- Roz raat 2 baje backup lo
- Har ghante disk space check karo
- Monday ko reports email karo
- Har minute server alive hai check karo

---

## 📋 Crontab — Schedule Likhne Ki Jagah

```bash
crontab -e                # Apna crontab edit karo (nano ya vim)
crontab -l                # Apna crontab dekho (list)
crontab -r                # Apna crontab DELETE karo (dhyan se!)
sudo crontab -u rahul -l  # Rahul ka crontab dekho
```

---

## 🕐 Cron Syntax — Time Format

```
* * * * * command
│ │ │ │ │
│ │ │ │ └── Day of week (0-7, 0 aur 7 = Sunday)
│ │ │ └──── Month (1-12)
│ │ └────── Day of month (1-31)
│ └──────── Hour (0-23)
└────────── Minute (0-59)

* = "har baar" (any value)
```

---

## 📅 Cron Examples — Ek Ek Samjho

```bash
# Roz raat 2 baje backup lo
0 2 * * * /home/rahul/backup.sh

# Har ghante ek baar kuch karo
0 * * * * /script/hourly.sh

# Har 5 minute pe kuch karo
*/5 * * * * /script/check.sh

# Har din subah 9 baje
0 9 * * * /script/morning.sh

# Sirf Monday ko (weekday 1) subah 8 baje
0 8 * * 1 /script/weekly_report.sh

# Har mahine ki 1 tarikh ko
0 0 1 * * /script/monthly.sh

# Roz har ghante kaam ke time (9am-5pm)
0 9-17 * * * /script/work_hours.sh

# Sirf weekdays (Monday-Friday)
0 9 * * 1-5 /script/weekday.sh

# Har 15 minute
*/15 * * * * /script/check.sh

# Reboot pe chalao
@reboot /script/startup.sh
```

---

## 🎯 Special Shortcuts

```bash
@reboot      # Boot pe ek baar
@hourly      # Har ghante   (= 0 * * * *)
@daily       # Roz midnight (= 0 0 * * *)
@weekly      # Har Sunday   (= 0 0 * * 0)
@monthly     # Har 1st      (= 0 0 1 * *)
@yearly      # Jan 1st      (= 0 0 1 1 *)
```

---

## 📝 Practical Cron Jobs

```bash
# Disk space log karo
*/30 * * * * df -h >> /home/rahul/disk_log.txt

# Roz backup lo
0 3 * * * tar -czvf /backup/home_$(date +\%Y\%m\%d).tar.gz /home/rahul/

# Log files saaf karo (7 din purani)
0 4 * * * find /var/log -name "*.log" -mtime +7 -delete

# Script output email karo
0 8 * * * /script/report.sh | mail -s "Daily Report" you@email.com
```

---

## 🔀 Output Redirect Karo

```bash
# Output aur errors file mein save karo
* * * * * /script/task.sh >> /var/log/task.log 2>&1

# Output ignore karo
* * * * * /script/task.sh > /dev/null 2>&1
```

---

## 🔍 Cron Debug Karna

```bash
# Cron service check karo
sudo systemctl status cron

# Cron ke logs dekho
sudo grep CRON /var/log/syslog
sudo tail -f /var/log/syslog | grep CRON

# Script manually test karo pehle!
bash /path/to/script.sh
```

---

## 🏋️ Practice

```bash
# Step 1: Simple script banao
nano /home/rahul/time_log.sh
```

```bash
#!/bin/bash
echo "$(date): Cron ne mujhe chalaya!" >> /home/rahul/cron_test.log
```

```bash
chmod +x /home/rahul/time_log.sh

# Step 2: Crontab mein add karo (har minute)
crontab -e
# Yeh line add karo:
# * * * * * /home/rahul/time_log.sh

# Step 3: 2-3 minute wait karo aur dekho
cat /home/rahul/cron_test.log

# Step 4: Crontab se hatao
crontab -e
# Line delete karo, save karo
```

---

## 📝 Aaj Ka Summary

✅ Cron = Automatic task scheduler
✅ `crontab -e` edit, `-l` list, `-r` remove
✅ Format: `Minute Hour Day Month Weekday Command`
✅ `*` = har baar
✅ `*/5` = har 5 minute
✅ `@daily`, `@reboot` shortcuts
✅ Output `>> logfile 2>&1` se save karo

---
**Day:** 16/30 | **Topic:** Cron Jobs & Automation | **Difficulty:** ⭐⭐⭐☆☆
