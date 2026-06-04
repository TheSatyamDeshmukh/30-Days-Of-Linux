# 📝 Day 18 Quiz — Firewall & Security

> **Tip:** `sudo ufw status` aur `sudo fail2ban-client status` chalao! 🛡️

---

## 🟢 Section A — Easy (1 point each)

**Q1.** UFW ka full form kya hai?
- A) Unix Firewall B) Uncomplicated Firewall C) Universal File Watcher D) Ubuntu Firewall

**Q2.** UFW enable karne ka command?
- A) `sudo ufw on` B) `sudo ufw start` C) `sudo ufw enable` D) `sudo firewall enable`

**Q3.** Port 80 (HTTP) allow karne ka command?
- A) `sudo ufw open 80` B) `sudo ufw allow 80` C) `sudo ufw permit 80` D) `sudo ufw add 80`

**Q4.** fail2ban kisliye use hota hai?
- A) File backup ke liye B) Brute force attacks automatically block karne ke liye C) Firewall manage karne ke liye D) Fail logs analyze karne ke liye

**Q5.** SSH ki security ke liye `PermitRootLogin no` kahan likhte hain?
- A) `/etc/ssh/ssh_config` B) `/etc/ssh/sshd_config` C) `~/.ssh/config` D) `/etc/security/ssh`

---

## 🟡 Section B — Medium (2 points each)

**Q6.** `sudo ufw default deny incoming` kya karta hai?
- A) Sab incoming traffic allow karo B) Default rule: koi bhi incoming connection allow mat karo C) DNS deny karo D) Download band karo

**Q7.** `sudo ufw status numbered` mein `numbered` kyun use karte hain?
- A) Rule ka number count ke liye B) Rules delete karne ke liye number se identify karna hai C) Numbered format zyada readable hai D) Port numbers dikhata hai

**Q8.** fail2ban mein `bantime = 3600` ka matlab?
- A) 3600 attempts ke baad ban B) 3600 seconds (1 ghanta) ke liye ban C) 3600 users ban D) Automatic unban 3600 se

**Q9.** SSH hardening mein `MaxAuthTries 3` kya karta hai?
- A) 3 users allow karo B) Max 3 login attempts, phir connection close C) 3 second timeout D) 3 keys allow

**Q10.** `sudo ufw reset` kya karta hai?
- A) UFW restart karta hai B) Sab UFW rules delete karke default state pe le jaata hai C) Rules reset karta hai D) UFW reinstall karta hai

---

## 🔴 Section C — Hard (3 points each)

**Q11.** Sirf `192.168.1.0/24` subnet ko SSH access deni hai. Command?
- A) `sudo ufw allow 22` B) `sudo ufw allow from 192.168.1.0/24 to any port 22` C) `sudo ufw allow ssh 192.168.1.0` D) `sudo ufw subnet allow 22`

**Q12.** `sudo fail2ban-client set sshd unbanip 1.2.3.4` kya karta hai?
- A) IP ban karta hai B) IP ko SSH jail se unban karta hai C) IP block karta hai D) IP whitelist mein add karta hai

**Q13.** Lynis kya hai?
- A) Linux distribution B) Security auditing tool — system ki security check karta hai aur recommendations deta hai C) Firewall tool D) Log analyzer

**Q14.** SSH `PasswordAuthentication no` ke baad kya hoga?
- A) SSH band ho jaayega B) Sirf SSH keys se login hoga — password se nahi C) Root login disable hoga D) All logins disable honge

**Q15.** `sudo find / -perm /4000 2>/dev/null` kya dhundhta hai?
- A) 4000 files B) SUID bit set files — root privileges se chalti hain C) 4000 KB files D) Permission 4000 wali files

---

## 🎯 Bonus (5 points each)

**Q16.** Naye production server pe security hardening ka sahi order kya hai?
- A) Kuch nahi karo B) Update → SSH harden → UFW setup → fail2ban → disable unused services → Lynis audit C) Sirf firewall D) Sirf password change

**Q17.** `last` command mein suspicious activity kya dikhi? Foreign IP se root login attempts. Agle steps?
- A) Ignore karo B) `sudo grep "Failed" /var/log/auth.log` → fail2ban check → UFW rules review → SSH config harden → Consider changing SSH port C) Server format karo D) Password change karo sirf

---

## ✅ ANSWERS

<details>
<summary>👆 Answers dekho</summary>

| Q# | Answer | Explanation |
|----|--------|-------------|
| Q1 | B | UFW = Uncomplicated Firewall — iptables ka easy wrapper |
| Q2 | C | `sudo ufw enable` |
| Q3 | B | `sudo ufw allow PORT` |
| Q4 | B | fail2ban = automatic IP ban after multiple failed attempts |
| Q5 | B | `sshd_config` = SSH daemon config. `ssh_config` = client config |
| Q6 | B | Default deny = whitelist approach — sirf explicitly allowed traffic andar |
| Q7 | B | `numbered` = numbers dikhata hai taaki `sudo ufw delete 3` se specific rule delete kar sako |
| Q8 | B | `bantime` = seconds mein ban duration. 3600 = 1 hour |
| Q9 | B | Brute force protection — 3 attempts ke baad connection drop |
| Q10 | B | `reset` = nuclear option — sab rules gone, disabled state |
| Q11 | B | Source IP range specify karte hain `from` se |
| Q12 | B | `unbanip` = IP ko whitelist karo, unban karo |
| Q13 | B | Lynis = security auditing tool `sudo lynis audit system` |
| Q14 | B | `PasswordAuthentication no` = only key-based auth |
| Q15 | B | SUID = Set User ID — execute karne pe file owner (often root) ke permissions se chalta hai |
| Q16 | B | Security layering — har step pehle wale pe build karta hai |
| Q17 | B | Systematic response: investigate → harden → monitor |

</details>

**Total Marks:** 50 | **Day:** 18/30 | **Topic:** Firewall & Security
