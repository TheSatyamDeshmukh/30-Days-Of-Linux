# 📝 Day 17 Quiz — Systemd & Services

> **Tip:** `systemctl status ssh` aur `systemd-analyze blame` chalao! 🏃

---

## 🟢 Section A — Easy (1 point each)

**Q1.** Systemd ka PID (Process ID) kya hota hai?
- A) 0 B) 1 C) 100 D) Random

**Q2.** Service start karne ka command?
- A) `service start nginx` B) `sudo systemctl start nginx` C) `sudo start nginx` D) `nginx --start`

**Q3.** Service ko boot pe automatically start karne ke liye?
- A) `sudo systemctl autostart nginx` B) `sudo systemctl enable nginx` C) `sudo systemctl boot nginx` D) `sudo service nginx enable`

**Q4.** Service ka status check karne ka command?
- A) `sudo systemctl check nginx` B) `sudo systemctl status nginx` C) `sudo service status nginx` D) `nginx --status`

**Q5.** `journalctl -f` kya karta hai?
- A) Journal filter karta hai B) Live system logs dikhata hai (tail -f jaisa) C) Journal format change karta hai D) Failed services dikhata hai

---

## 🟡 Section B — Medium (2 points each)

**Q6.** `systemctl enable --now nginx` kya karta hai?
- A) Sirf enable karta hai B) Enable + abhi start bhi karta hai — ek command mein dono C) Now mode enable D) Nginx update karta hai

**Q7.** `systemctl reload nginx` aur `systemctl restart nginx` mein kya fark hai?
- A) Koi fark nahi B) `reload` = config reload (service band nahi hoti), `restart` = stop + start (downtime) C) `reload` faster hai D) `restart` sirf config reload karta hai

**Q8.** `journalctl -u nginx --since "1 hour ago"` kya dikhata hai?
- A) Nginx install history B) Pichle 1 ghante ke nginx logs C) Nginx ki 1 line D) Nginx errors sirf

**Q9.** Failed services list karne ka command?
- A) `systemctl list-failed` B) `systemctl list-units --state=failed` C) Dono kaam karte hain D) `journalctl --failed`

**Q10.** `.service` file kahan hoti hai?
- A) `/home/services/` B) `/etc/systemd/system/` C) `/var/service/` D) `/usr/service/`

---

## 🔴 Section C — Hard (3 points each)

**Q11.** `.service` file mein `After=network.target` ka kya matlab hai?
- A) Network ke baad service start hogi B) Service ke baad network start hoga C) Network required nahi D) Service network use nahi karegi

**Q12.** `systemd-analyze blame` kya karta hai?
- A) Boot errors blame karta hai B) Har service ne boot mein kitna time liya — performance analysis C) Failed services blame karta hai D) Disk usage dikhata hai

**Q13.** Service crash ke baad automatically restart karne ke liye `.service` file mein kya likhna hoga?
- A) `AutoRestart=yes` B) `Restart=on-failure` C) `RestartAlways=true` D) `OnCrash=restart`

**Q14.** `journalctl -p err` kya filter karta hai?
- A) Error priority aur upar ke logs (emergency, alert, critical, error) B) Sirf exact "err" string C) Error files D) Process errors

**Q15.** Systemd units kitne types ke hote hain?
- A) Sirf .service B) .service, .socket, .timer, .mount, .target, .device aur aur bhi C) .service aur .config D) .service aur .socket sirf

---

## 🎯 Bonus (5 points each)

**Q16.** Ek service bar bar crash ho rahi hai. Troubleshoot karne ke steps?
- A) Service delete karo B) `systemctl status service` → `journalctl -u service -n 50` → config check → restart C) Reinstall Linux D) Server restart

**Q17.** `systemctl daemon-reload` kab chalana zaroori hai?
- A) Kabhi nahi B) Jab bhi koi `.service` file create ya modify ki ho — systemd ko nayi file detect karni hoti hai C) Har reboot ke baad D) Service start karne se pehle hamesha

---

## ✅ ANSWERS

<details>
<summary>👆 Answers dekho</summary>

| Q# | Answer | Explanation |
|----|--------|-------------|
| Q1 | B | Systemd = PID 1 — pehla process jo kernel start karta hai |
| Q2 | B | `systemctl start servicename` |
| Q3 | B | `enable` = symlink banata hai — boot pe start hoga |
| Q4 | B | `systemctl status` = active/inactive, recent logs, PID |
| Q5 | B | `-f` = follow (live stream) |
| Q6 | B | `--now` = enable + start in one command |
| Q7 | B | `reload` = graceful config reload (zero downtime). `restart` = full restart |
| Q8 | B | `-u` = unit filter, `--since` = time filter |
| Q9 | C | Dono commands same result dete hain |
| Q10 | B | Custom service files = `/etc/systemd/system/`. System files = `/lib/systemd/system/` |
| Q11 | A | `After=` = ordering — is service se pehle woh start ho |
| Q12 | B | Boot time analysis — optimize karo |
| Q13 | B | `Restart=on-failure` = crash hone pe automatic restart |
| Q14 | A | Priority 0-3 (emerg, alert, crit, err) sab show karta hai |
| Q15 | B | Multiple unit types — service, socket, timer, mount, target, etc. |
| Q16 | B | Systematic debugging: status → logs → config → fix → restart |
| Q17 | B | `daemon-reload` = systemd ko new/modified unit files reload karne ke liye |

</details>

**Total Marks:** 50 | **Day:** 17/30 | **Topic:** Systemd & Services
