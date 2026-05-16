# 📝 Day 8 Quiz — Processes & Jobs

> **Tip:** `ps aux` aur `top` terminal mein chalao, output dekho, phir quiz do! ⚡

---

## 🟢 Section A — Easy (1 point each)

---

**Q1.** Process kya hota hai Linux mein?

- A) Ek file
- B) Ek running program — jab koi program chalta hai toh woh process ban jaata hai
- C) Ek folder
- D) Ek user

---

**Q2.** PID ka full form kya hai?

- A) Program Identifier
- B) Process ID
- C) Primary ID
- D) Program Instance Directory

---

**Q3.** `top` command kya karta hai?

- A) File ka top dikhata hai
- B) Live running processes monitor karta hai
- C) System reboot karta hai
- D) Top-level folders dikhata hai

---

**Q4.** Process kill karne ka command kya hai?

- A) `stop PID`
- B) `end PID`
- C) `kill PID`
- D) `terminate PID`

---

**Q5.** Command ke baad `&` lagane se kya hota hai?

- A) Command error deta hai
- B) Command background mein chalta hai
- C) Command cancel hota hai
- D) Command repeat hota hai

---

## 🟡 Section B — Medium (2 points each)

---

**Q6.** `ps aux` mein `a`, `u`, `x` flags ka kya matlab hai?

- A) Admin users, Unix format, eXtra info
- B) All users ke processes, User-readable format, processes without terminal bhi
- C) Active, Used, eXecuted processes
- D) Sirf formatting options hain

---

**Q7.** `kill -9 PID` aur `kill PID` mein kya fark hai?

- A) Koi fark nahi
- B) `kill PID` = polite request (SIGTERM — process khud band ho), `kill -9` = force kill (SIGKILL — instantly)
- C) `kill -9` = 9 processes kill karta hai
- D) `kill PID` sirf root use kar sakta hai

---

**Q8.** `Ctrl + Z` terminal mein kya karta hai?

- A) Process permanently delete karta hai
- B) Running process ko suspend (pause) karta hai aur background mein bhej deta hai
- C) Terminal band karta hai
- D) Last command undo karta hai

---

**Q9.** `jobs` command kya dikhata hai?

- A) Available jobs (naaukri listings!)
- B) Current terminal session ke background/suspended jobs
- C) Cron jobs
- D) System jobs (services)

---

**Q10.** `fg` command kya karta hai?

- A) Foreground color change karta hai
- B) Background job ko foreground mein wapas laata hai
- C) File generate karta hai
- D) Firefox open karta hai

---

## 🔴 Section C — Hard (3 points each)

---

**Q11.** `ps aux` output mein yeh line hai:
```
rahul   1234  99.0  2.5  12345  6789  S   python3 myscript.py
```
Iska kya matlab hai?

- A) rahul ka python script chal raha hai, PID 1234 hai, 99% CPU le raha hai
- B) 1234 files process ho rahi hain
- C) 99 users python use kar rahe hain
- D) Script 2.5 ghante se chal raha hai

---

**Q12.** STAT column mein `Z` ka kya matlab hai?

- A) Sleeping process
- B) Zombie process — band ho gaya par parent ne abhi accept nahi kiya
- C) Zero CPU usage
- D) Zipped/compressed process

---

**Q13.** Ek process hai jo `kill PID` se band nahi ho raha. Kya karoge?

- A) Computer restart karo
- B) `kill -9 PID` use karo — SIGKILL force terminate karta hai
- C) `killall PID` use karo
- D) Thoda wait karo

---

**Q14.** `nproc` command kya batata hai?

- A) Network processes
- B) New processes count
- C) CPU cores ki sankhya
- D) Running processes count

---

**Q15.** Load average `2.50 1.75 1.25` ka kya matlab hai single-core system pe?

- A) System bilkul normal hai
- B) 1 minute average 2.5 hai — 1-core system ke liye 250% load — overloaded!
- C) 2.5 users logged in hain
- D) 2.5 GB RAM use ho rahi hai

---

## 🔴 Section D — Scenario Based (3 points each)

---

**Q16.** Tumne yeh chalaya:
```bash
sleep 500 &
sleep 600 &
jobs
```
`jobs` ka output kaisa dikhega?

- A) Kuch nahi
- B) `[1]- Running sleep 500 &` aur `[2]+ Running sleep 600 &`
- C) Sirf last job
- D) Error

---

**Q17.** Firefox hang ho gaya hai, close nahi ho raha. Terminal se kaise fix karoge?

- A) `stop firefox`
- B) `ps aux | grep firefox` se PID nikalo, phir `kill -9 PID`
- C) `killall -soft firefox`
- D) `rm firefox`

---

**Q18.** `free -h` output hai:
```
              total   used   free
Mem:           8.0G   7.8G   200M
Swap:          2.0G   1.5G   500M
```
System ki kya condition hai?

- A) Bilkul normal
- B) RAM almost full hai, swap bhi heavily used hai — performance slow hogi
- C) Disk full hai
- D) Network slow hai

---

## 🎯 Bonus (5 points each)

---

**Q19.** Ek long-running script chal rahi hai. Tum SSH connection band karna chahte ho par script band nahi karni. Kya karoge?

- A) Terminal band karo — script apne aap chalti rahegi
- B) `nohup script.sh &` use karo ya `screen`/`tmux` — SSH disconnect ke baad bhi chalti rahegi
- C) Kuch nahi kar sakte
- D) Script ko background mein bhejo `Ctrl+Z` se

---

**Q20.** `htop` mein kaunse features `top` se better hain? (Sahi option choose karo)

- A) htop mein koi farak nahi, sirf naam alag hai
- B) htop = colorful, mouse support, tree view, process directly select karke kill karo — `top` se zyada user-friendly
- C) htop sirf root use kar sakta hai
- D) htop sirf RAM dikhata hai

---

---

## ✅ ANSWERS

<details>
<summary>👆 Click karke Answers dekho!</summary>

| Q# | Answer | Explanation |
|----|--------|-------------|
| Q1 | **B** | Process = running program. Chrome khola = ek process. Multiple tabs = multiple processes |
| Q2 | **B** | PID = Process ID — har process ka unique number hota hai |
| Q3 | **B** | `top` = live process monitor. `q` dabao exit ke liye |
| Q4 | **C** | `kill PID` — default SIGTERM (15) bhejta hai |
| Q5 | **B** | `&` = background mein chalao — terminal free rehti hai |
| Q6 | **B** | `a`=all users, `u`=user format, `x`=no terminal processes bhi |
| Q7 | **B** | `kill` = SIGTERM (please stop), `kill -9` = SIGKILL (FORCE stop — no cleanup) |
| Q8 | **B** | `Ctrl+Z` = SIGTSTP — process suspend. Phir `bg` se background mein bhejo |
| Q9 | **B** | `jobs` = current shell ke background/suspended jobs list karta hai |
| Q10 | **B** | `fg` = foreground mein laao. `fg %1` = job number 1 |
| Q11 | **A** | Format: USER PID %CPU %MEM VSZ RSS STAT COMMAND |
| Q12 | **B** | Zombie = process exit ho gaya but parent ne wait() nahi kiya — entry table mein hai |
| Q13 | **B** | `kill -9` = SIGKILL — kernel directly terminate karta hai, process cleanup nahi kar sakta |
| Q14 | **C** | `nproc` = number of processing units (CPU cores/threads) |
| Q15 | **B** | Load avg 2.5 on 1 core = 250% utilization = 1.5 processes wait kar rahe hain! |
| Q16 | **B** | `&` se background chalaye, `jobs` dono dikhata hai numbered |
| Q17 | **B** | `ps aux | grep firefox` → PID nikalo → `kill -9 PID` ya seedha `killall -9 firefox` |
| Q18 | **B** | RAM 97.5% used + Swap 75% used = serious memory pressure! |
| Q19 | **B** | `nohup` = "no hangup" — SSH close ho toh bhi process chalta rahe. `screen`/`tmux` bhi best options hain |
| Q20 | **B** | htop = mouse support, color coding, F-key shortcuts, tree view — much better UX |

</details>

---

## 📊 Score Calculator

| Score | Result |
|-------|--------|
| 52-60 | 🏆 **Process Master!** |
| 39-51 | 🥈 **Good!** |
| 26-38 | 🥉 **Thodi practice** |
| 0-25  | 📖 **DAY-8.md dobara padho** |

**Total Marks:** 60

---

## 💻 Practical Challenge

```bash
# 1. Background process chalao
sleep 500 &
sleep 600 &

# 2. Jobs dekho
jobs

# 3. ps se confirm karo
ps aux | grep sleep

# 4. PID note karo aur kill karo
kill %1           # Job number 1 kill karo
jobs              # Ab sirf ek hai

# 5. Dusra bhi kill karo
kill %1

# 6. Top dekho (5 seconds)
top -b -n 1 | head -20

# 7. RAM check karo
free -h

# 8. CPU cores
nproc
uptime
```

---
**Quiz:** Day 8/30 | **Total Marks:** 60 | **Topic:** Processes & Jobs
