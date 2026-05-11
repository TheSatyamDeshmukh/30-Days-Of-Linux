# 📝 Day 3 Quiz — Linux File System

> **Instructions:** Har question dhyan se padho — file system questions tricky hote hain!
> Terminal mein `ls /` chalao aur folders khud dekho phir quiz do! 🗂️

---

## 🟢 Section A — Easy (1 point each)

---

**Q1.** Linux ka root directory kaun sa hota hai?

- A) `/home`
- B) `/root`
- C) `/` (single slash)
- D) `C:\`

---

**Q2.** Tumhara personal home folder kahan hota hai?

- A) `/home/username`
- B) `/personal/username`
- C) `/users/username`
- D) `/my/username`

---

**Q3.** System configuration files kahan hoti hain?

- A) `/bin`
- B) `/home`
- C) `/etc`
- D) `/usr`

---

**Q4.** `/tmp` folder ke baare mein kya sach hai?

- A) Yahan important files rakhte hain
- B) Computer restart hone pe iska saara content delete ho jaata hai
- C) Sirf root user use kar sakta hai
- D) Yeh folder hamesha empty hota hai

---

**Q5.** `~` (tilde) ka kya matlab hota hai Linux mein?

- A) Root directory
- B) Tumhara home folder (shortcut)
- C) Hidden folder
- D) System folder

---

## 🟡 Section B — Medium (2 points each)

---

**Q6.** `/var/log` folder mein kya hota hai?

- A) Video files
- B) System log files
- C) User passwords
- D) Installed programs

---

**Q7.** Yeh command kya output dega?
```bash
cat /etc/os-release | grep PRETTY_NAME
```

- A) Computer ka naam
- B) Linux distribution ka naam aur version
- C) System uptime
- D) Memory information

---

**Q8.** `/dev/null` kya hota hai?

- A) Ek error file
- B) Ek empty device — jo bhi bhejo woh discard ho jaata hai (black hole!)
- C) Development folder
- D) Network device

---

**Q9.** Programs ke basic commands (ls, cp, mv) kahan hote hain?

- A) `/home`
- B) `/etc`
- C) `/bin`
- D) `/var`

---

**Q10.** `/proc` directory ke baare mein kya sach hai?

- A) Yeh ek normal folder hai hard disk pe
- B) Yahan process files store hoti hain permanently
- C) Yeh ek virtual filesystem hai — kernel ki live information yahan hoti hai
- D) Yeh programs ka folder hai

---

## 🔴 Section C — Path Navigation (3 points each)

---

**Q11.** Agar tum `/home/rahul/Documents` mein ho aur `cd ../../bin` type karo, tum kahan pahunchoge?

- A) `/home/bin`
- B) `/bin`
- C) `/home/rahul/bin`
- D) Error aayega

---

**Q12.** Yeh command kya check karta hai?
```bash
cat /proc/meminfo | grep MemTotal
```

- A) Memory ka total amount
- B) Memory file ka naam
- C) Memory errors
- D) Memory processes

---

**Q13.** `/usr/bin` aur `/bin` mein kya fark hai?

- A) Koi fark nahi, dono same hain
- B) `/bin` mein basic system commands hain jo boot ke liye zaroori hain, `/usr/bin` mein additional programs hain
- C) `/usr/bin` sirf users ke liye hai, `/bin` sirf admin ke liye
- D) `/bin` khali hota hai

---

**Q14.** Agar koi file path `/home/rahul/projects/linux/notes.txt` hai, toh root se kitne levels deep hai?

- A) 3 levels
- B) 4 levels
- C) 5 levels
- D) 6 levels

---

**Q15.** `df -h` command kya dikhata hai?

- A) Default folder list
- B) Disk free space — kitna space available hai har partition pe
- C) Directory files
- D) Default home folder

---

## 🔴 Section D — Fill in the Blank (3 points each)

Sahi folder naam choose karo:

---

**Q16.** Web server (nginx/apache) ki files generally kahan hoti hain?

- A) `/home/www`
- B) `/var/www`
- C) `/etc/www`
- D) `/usr/www`

---

**Q17.** Boot files aur Linux kernel kahan hota hai?

- A) `/kernel`
- B) `/system`
- C) `/boot`
- D) `/start`

---

**Q18.** Third-party software jo system package manager se install nahi hua, usse kahan rakhte hain?

- A) `/bin`
- B) `/home`
- C) `/opt`
- D) `/extra`

---

## 🎯 Bonus — Real Scenario (5 points)

**Q19.** Ek server pe kaam kar rahe ho. Suddenly disk space full ho gayi. Tum kaunse command se check karoge ki kaun sa folder sabse zyada space le raha hai?

- A) `ls -la /`
- B) `du -sh /* 2>/dev/null | sort -rh | head -10`
- C) `cat /proc/diskinfo`
- D) `find / -large`

---

**Q20.** Agar tumhe Linux ka exact version check karna ho, kaun sa file padho?

- A) `/etc/version`
- B) `/proc/linux`
- C) `/etc/os-release`
- D) `/var/linux-version`

---

---

## ✅ ANSWERS

<details>
<summary>👆 Click karo — Answers dekho</summary>

| Q# | Answer | Explanation |
|----|--------|-------------|
| Q1 | **C** | `/` = root — sabse upar ka folder, sab isi se start hota hai |
| Q2 | **A** | `/home/username` — jaise `/home/rahul` — tumhara personal space |
| Q3 | **C** | `/etc` = "Everything To Configure" — sab system configs yahan |
| Q4 | **B** | `/tmp` reboot pe saaf ho jaata hai — temporary files ke liye |
| Q5 | **B** | `~` = home directory shortcut — `cd ~` = ghar wapas |
| Q6 | **B** | `/var/log` mein system ke log files hoti hain — errors, warnings sab |
| Q7 | **B** | OS ka naam aur version — jaise "Ubuntu 22.04.3 LTS" |
| Q8 | **B** | `/dev/null` = black hole — output discard karne ke liye use karte hain |
| Q9 | **C** | `/bin` mein basic commands hain — ls, cp, mv, cat sab yahan! |
| Q10 | **C** | `/proc` virtual filesystem hai — RAM mein hota hai, disk pe nahi |
| Q11 | **B** | `/home/rahul/Documents` → `..` = `/home/rahul` → `..` = `/home` → `..` = `/` → `bin` = `/bin` |
| Q12 | **A** | `MemTotal` se pata chalta hai system mein total RAM kitni hai |
| Q13 | **B** | `/bin` = core system commands (boot ke liye), `/usr/bin` = additional programs |
| Q14 | **C** | `/`(1) `home`(2) `rahul`(3) `projects`(4) `linux`(5) — 5 levels |
| Q15 | **B** | `df` = disk free — `-h` = human readable (GB/MB mein) |
| Q16 | **B** | `/var/www` — web server files yahan hoti hain (variable data) |
| Q17 | **C** | `/boot` mein kernel (vmlinuz) aur GRUB bootloader hota hai |
| Q18 | **C** | `/opt` = optional software — third-party apps ke liye |
| Q19 | **B** | `du -sh /*` se har folder ka size, `sort -rh` se bade pehle, `head -10` se top 10 |
| Q20 | **C** | `/etc/os-release` — Linux distribution ki detailed info |

</details>

---

## 📊 Score Calculator

| Score | Result |
|-------|--------|
| 45-55 | 🏆 **File System Expert!** |
| 33-44 | 🥈 **Good Understanding!** |
| 22-32 | 🥉 **Thodi aur practice** |
| 0-21  | 📖 **DAY-3.md dobara padho** |

**Total Marks:** 55 (Easy:5 + Medium:10 + Navigation:15 + Fill:9 + Bonus:10 + Explore:6)

---

## 💻 Practical Challenge

```bash
# Challenge: File system explorer ban jao!

# 1. Kitni files hain /etc mein?
ls /etc | wc -l

# 2. Tumhara CPU kaun sa hai?
cat /proc/cpuinfo | grep "model name" | head -1

# 3. Total RAM kitni hai?
cat /proc/meminfo | grep MemTotal

# 4. Disk space check karo
df -h

# 5. Kaun sa Linux hai?
cat /etc/os-release | grep PRETTY_NAME

# 6. /tmp mein kya hai?
ls /tmp

# 7. Bada folder kaun sa hai?
du -sh /var /usr /home /etc 2>/dev/null | sort -rh
```

---

*"File system samajh gaye toh Linux ka 50% kaam ho gaya!"* 🗂️

---
**Quiz:** Day 3/30 | **Total Marks:** 55 | **Topic:** Linux File System
