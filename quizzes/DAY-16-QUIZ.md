# 📝 Day 16 Quiz — Cron Jobs & Automation

> **Tip:** `crontab -l` aur `crontab -e` try karo! ⏰

---

## 🟢 Section A — Easy (1 point each)

**Q1.** Cron kisliye use hota hai?
- A) Files compress karne ke liye B) Tasks automatically schedule karne ke liye C) Processes kill karne ke liye D) Network monitor karne ke liye

**Q2.** `crontab -e` kya karta hai?
- A) Existing crontab execute karta hai B) Crontab edit karne ke liye kholta hai C) Crontab delete karta hai D) Crontab export karta hai

**Q3.** Cron syntax mein `*` ka kya matlab hai?
- A) All files B) Har value — "always" C) Admin only D) Error

**Q4.** `crontab -l` kya karta hai?
- A) Latest cron job chalata hai B) Current user ke cron jobs list karta hai C) Lock crontab D) Log dekho

**Q5.** `@daily` shortcut ka matlab kya hai?
- A) `* * * * *` B) `0 0 * * *` — har roz midnight C) `0 * * * *` D) `* * * * 0`

---

## 🟡 Section B — Cron Syntax Decode (2 points each)

**Q6.** `0 2 * * *` kab chalega?
- A) Har 2 minute B) Har roz raat 2 baje C) Month ka 2nd din D) 2 ghante baad

**Q7.** `*/5 * * * *` kab chalega?
- A) Month ka har 5th din B) Har 5 minute C) 5 baje D) Sirf 5th month mein

**Q8.** `0 9 * * 1` kab chalega?
- A) Har roz 9 baje B) Month ki 9 tarikh C) Har Monday subah 9 baje D) September mein

**Q9.** `0 0 1 * *` kab chalega?
- A) Har roz midnight B) Har mahine ki 1 tarikh midnight ko C) Har minute D) January 1st

**Q10.** `0 9-17 * * 1-5` kab chalega?
- A) 9 se 17 tak har ghante, weekdays (Mon-Fri) B) Sirf weekends C) Har din 9 baje D) Mahine mein ek baar

---

## 🔴 Section C — Hard (3 points each)

**Q11.** Cron job ka output `/dev/null` pe bhejne ka matlab?
- A) Output save karo B) Output completely discard karo — koi log nahi C) Output print karo D) Output email karo

**Q12.** `* * * * * /script/check.sh >> /var/log/check.log 2>&1` mein `2>&1` ka matlab?
- A) 2 baar run karo B) stderr (errors) bhi stdout ke saath file mein likho C) 2nd script D) Duplicate output

**Q13.** Cron job kaam nahi kar raha — debug kaise karoge?
- A) Restart karo B) `sudo grep CRON /var/log/syslog` se cron logs check karo C) Crontab delete karo D) `cron -debug`

**Q14.** `@reboot /home/rahul/startup.sh` kab chalega?
- A) Har reboot ke baad ek baar B) Har minute C) Sirf pehli baar D) Manually

**Q15.** Cron job mein full path kyun likhna chahiye commands ke liye?
- A) Cron environment mein `PATH` limited hota hai — `ls` bhi nahi milta sometimes B) Performance ke liye C) Security ke liye D) Koi zaroorat nahi

---

## 🎯 Bonus (5 points each)

**Q16.** Har Sunday raat 3 baje `/backup/` mein backup lena hai. Cron entry kya hogi?
- A) `0 3 * * 0 /home/rahul/backup.sh` B) `3 0 * * 7 backup.sh` C) `* * * * 0 /backup.sh` D) `0 3 0 0 0 /backup.sh`

**Q17.** Cron job daalne ke baad `crontab -l` se dikh raha hai, par run nahi ho raha. Possible reason?
- A) Cron service band hai — `sudo systemctl status cron` check karo B) Crontab format galat hai C) Script mein `#!/bin/bash` nahi hai D) Sab possible reasons hain — sab check karo

---

## ✅ ANSWERS

<details>
<summary>👆 Answers dekho</summary>

| Q# | Answer | Explanation |
|----|--------|-------------|
| Q1 | B | Cron = task scheduler — set once, runs automatically |
| Q2 | B | `crontab -e` = edit. `-l`=list, `-r`=remove |
| Q3 | B | `*` = any value — "every" |
| Q4 | B | `crontab -l` = list current user's cron jobs |
| Q5 | B | `@daily` = `0 0 * * *` = midnight daily |
| Q6 | B | Minute=0, Hour=2, Day=any, Month=any, Weekday=any = 2 AM daily |
| Q7 | B | `*/5` = every 5 (0,5,10,15...55) |
| Q8 | C | Hour=9, Weekday=1(Monday) = every Monday at 9 AM |
| Q9 | B | Day=1, Month=any = 1st of every month at midnight |
| Q10 | A | Hour=9-17 (range), Weekday=1-5 (Mon-Fri) = business hours |
| Q11 | B | `/dev/null` = black hole. `> /dev/null 2>&1` = discard all output |
| Q12 | B | `2>&1` = redirect stderr(2) to stdout(1) — errors bhi log file mein |
| Q13 | B | Cron logs `/var/log/syslog` mein hote hain |
| Q14 | A | `@reboot` = once after each system reboot |
| Q15 | A | Cron PATH = `/usr/bin:/bin` only. `/usr/local/bin` etc. included nahi |
| Q16 | A | `0 3 * * 0` — 0=Sunday (weekday 0 ya 7) |
| Q17 | D | Multiple reasons possible — systematic check karo |

</details>

**Total Marks:** 50 | **Day:** 16/30 | **Topic:** Cron Jobs
