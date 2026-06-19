# 📝 Day 19 Quiz — Log Management

> **Tip:** `sudo tail -f /var/log/syslog` aur `journalctl -f` try karo! 📋

---

## 🟢 Section A — Easy (1 point each)

**Q1.** System logs kahan hote hain?
- A) `/home/logs/` B) `/var/log/` C) `/etc/logs/` D) `/tmp/logs/`

**Q2.** Live logs dekhne ka command (tail follow mode)?
- A) `tail log.txt` B) `tail -f /var/log/syslog` C) `cat -live log.txt` D) `watch log.txt`

**Q3.** `journalctl -u nginx` kya dikhata hai?
- A) Nginx install history B) Nginx service ke logs C) Nginx config D) Nginx files

**Q4.** Failed SSH login attempts kahan milenge?
- A) `/var/log/nginx/` B) `/var/log/auth.log` C) `/var/log/messages` D) `/var/log/boot.log`

**Q5.** Log file mein "error" dhundhne ka command?
- A) `find "error" log.txt` B) `grep "error" /var/log/syslog` C) `search error log.txt` D) `cat log.txt | error`

---

## 🟡 Section B — Medium (2 points each)

**Q6.** `journalctl --since "2 hours ago"` kya karta hai?
- A) 2 ghante ke log delete karta hai B) Pichle 2 ghante ke logs dikhata hai C) 2 ghante baad logs dikhata hai D) Log file 2 ghante mein save karta hai

**Q7.** `journalctl -p err` mein `-p err` ka matlab?
- A) Print errors B) Priority filter — error aur upar ki severity ke logs C) Path errors D) Process errors

**Q8.** `logrotate` kisliye use hota hai?
- A) Logs rotate (spin) karta hai B) Log files automatically compress, archive, delete karta hai jab bade ho jaate hain C) Logs encrypt karta hai D) Logs backup karta hai

**Q9.** `sudo journalctl --vacuum-size=100M` kya karta hai?
- A) 100MB logs create karta hai B) Journal logs 100MB tak rakhta hai, baki delete karta hai C) Vacuum cleaner mode D) 100 log files rakhta hai

**Q10.** `grep -i "failed" /var/log/auth.log | tail -20` kya karta hai?
- A) 20 files dhundhta hai B) auth.log mein "failed" (case-insensitive) dhundh ke aakhri 20 matching lines dikhata hai C) 20 errors fix karta hai D) Last 20 minutes ke logs

---

## 🔴 Section C — Hard (3 points each)

**Q11.** Log levels sahi order mein (most severe se least)?
- A) info, warning, error, critical B) emerg, alert, crit, err, warning, notice, info, debug C) debug, info, warning, error D) error, warning, info, debug

**Q12.** `journalctl -b -1` kya dikhata hai?
- A) Current boot ke logs B) Pichle boot ke logs C) Aakhri ek ghante ke logs D) Boot errors

**Q13.** Nginx access log format mein kya hota hai typically?
- A) Sirf errors B) IP, date/time, request method, URL, status code, response size C) Sirf response codes D) User agents sirf

**Q14.** `/var/log/` ka size bahut bada ho gaya. Kya karoge?
- A) Delete all logs B) `sudo journalctl --vacuum-time=30d` aur old `.gz` files delete, logrotate config check C) Ignore D) New disk add karo

**Q15.** `lastb` command kya dikhata hai?
- A) Last backup B) Failed login attempts (bad logins) C) Last boot D) Last backup

---

## 🎯 Bonus (5 points each)

**Q16.** Production server pe security incident investigate karna hai — suspicious activity 3 days pehle thi. Commands kya use karoge?
- A) `ls /var/log` B) `sudo journalctl --since "3 days ago" -p warning` + `sudo grep "Failed\|Invalid\|error" /var/log/auth.log` C) `cat /var/log/syslog` D) Restart karo

**Q17.** Real-time monitoring setup karna hai jo ERROR ya CRITICAL log hone pe alert kare. Basic approach?
- A) Manually check karo B) `tail -f /var/log/syslog | grep -i "error\|critical" | while read line; do echo "ALERT: $line" | mail -s "Server Alert" admin@email.com; done` C) Koi tool nahi hai D) Nagios only use karo

---

## ✅ ANSWERS

<details>
<summary>👆 Answers dekho</summary>

| Q# | Answer | Explanation |
|----|--------|-------------|
| Q1 | B | `/var/log/` = standard log directory |
| Q2 | B | `tail -f` = follow mode, live stream |
| Q3 | B | `-u nginx` = unit filter |
| Q4 | B | `auth.log` = authentication events (Ubuntu). `secure` on CentOS |
| Q5 | B | `grep "pattern" file` |
| Q6 | B | `--since` = time filter |
| Q7 | B | `-p` = priority. err=3, warning=4, info=6, debug=7 |
| Q8 | B | logrotate = log lifecycle management |
| Q9 | B | `--vacuum-size` = size limit |
| Q10 | B | `grep -i` = case insensitive, `tail -20` = last 20 matches |
| Q11 | B | Syslog severity: 0=emerg, 1=alert, 2=crit, 3=err, 4=warn, 5=notice, 6=info, 7=debug |
| Q12 | B | `-b` = boot. `-b 0`=current, `-b -1`=previous |
| Q13 | B | Combined log format: IP - - [date] "method URL" status size |
| Q14 | B | Systematic cleanup — vacuum + old files + config review |
| Q15 | B | `lastb` = bad logins. `last` = successful logins |
| Q16 | B | Time-based filter + auth log grep |
| Q17 | B | Real-time pipe monitoring — production mein Prometheus/Grafana use karte hain |

</details>

**Total Marks:** 50 | **Day:** 19/30 | **Topic:** Log Management
