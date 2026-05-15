# 📝 Day 6 Quiz — Users & Groups

> **Tip:** `cat /etc/passwd` aur `groups` commands terminal mein chalao phir quiz do! 👤

---

## 🟢 Section A — Easy (1 point each)

---

**Q1.** `whoami` command kya karta hai?

- A) System info dikhata hai
- B) Current logged-in user ka naam dikhata hai
- C) Password change karta hai
- D) User list dikhata hai

---

**Q2.** Linux mein sabse powerful user kaun hota hai?

- A) admin
- B) superuser
- C) root
- D) owner

---

**Q3.** Naya user banane ka command kya hai?

- A) `adduser`
- B) `newuser`
- C) `useradd`
- D) A aur C dono

---

**Q4.** `passwd` command kisliye use hota hai?

- A) Password dekhne ke liye
- B) Password set ya change karne ke liye
- C) Password delete karne ke liye
- D) Password backup ke liye

---

**Q5.** `sudo` ka full form kya hai?

- A) Super User Download
- B) Super User Do
- C) System User Do
- D) Secure User Do

---

## 🟡 Section B — Medium (2 points each)

---

**Q6.** `/etc/passwd` file mein kya hota hai?

- A) Users ke passwords
- B) Users ki list aur unki basic info (UID, home, shell)
- C) System passwords
- D) Network passwords

---

**Q7.** User ko `sudo` group mein add karne ka sahi command kya hai?

- A) `sudo addgroup rahul sudo`
- B) `sudo usermod -aG sudo rahul`
- C) `sudo groupadd rahul sudo`
- D) `sudo chmod sudo rahul`

---

**Q8.** `usermod -aG` mein `-a` flag kyun zaroori hai?

- A) Admin permission deta hai
- B) Bina `-a` ke purane groups remove ho jaate hain — `-a` = append (add only)
- C) Authentication enable karta hai
- D) Automatic mode hai

---

**Q9.** `su - priya` aur `su priya` mein kya fark hai?

- A) Koi fark nahi
- B) `su -` priya ka poora environment load karta hai, `su` sirf user switch karta hai
- C) `su -` temporary hai, `su` permanent
- D) `su -` root ke liye, `su` normal users ke liye

---

**Q10.** User delete karte waqt `-r` flag ka kya matlab hai?

- A) Root permission se delete karo
- B) Home folder bhi delete karo user ke saath
- C) Recursive delete
- D) Force delete

---

## 🔴 Section C — Hard (3 points each)

---

**Q11.** `/etc/passwd` ki ek line hai:
```
rahul:x:1000:1000:Rahul Kumar:/home/rahul:/bin/bash
```
Iska structure kya hai?

- A) name:password:UID:GID:comment:home:shell
- B) name:UID:GID:home:shell:comment:password
- C) name:password:home:shell:UID:GID:comment
- D) name:shell:home:UID:GID:comment:password

---

**Q12.** Ek user `priya` hai jo `developers` group mein nahi hai. Tum chahte ho ki woh `/var/www/html` folder ko edit kar sake jiska group `developers` hai. Kya karna hoga?

- A) `chmod 777 /var/www/html`
- B) `sudo usermod -aG developers priya`
- C) `sudo chown priya /var/www/html`
- D) `sudo passwd priya`

---

**Q13.** `id` command ka output hai:
```
uid=1000(rahul) gid=1000(rahul) groups=1000(rahul),27(sudo),999(docker)
```
Iska matlab kya hai?

- A) rahul ka UID 1000 hai, primary group rahul hai, aur woh sudo aur docker groups mein bhi hai
- B) rahul ke 3 users hain
- C) rahul ka password 1000 hai
- D) rahul ke 3 folders hain

---

**Q14.** Account lock karne ka command kya hai (login band karne ke liye)?

- A) `sudo usermod -d rahul`
- B) `sudo passwd -l rahul`
- C) `sudo userdel rahul`
- D) `sudo chmod -x rahul`

---

**Q15.** `w` command kya dikhata hai?

- A) Sirf current user
- B) Abhi kaun kaun logged in hai aur woh kya kar rahe hain
- C) System warnings
- D) Web connections

---

## 🔴 Section D — Scenario Based (3 points each)

---

**Q16.** Tumhare server pe ek naya developer `alex` aaya hai. Use:
- Login karna hai (bash shell)
- Home folder chahiye
- sudo access chahiye
- docker group mein bhi rehna hai

Sahi commands kaun si hain?

- A) `useradd alex`
- B) `sudo useradd -m -s /bin/bash alex && sudo passwd alex && sudo usermod -aG sudo,docker alex`
- C) `sudo adduser alex sudo docker`
- D) `sudo createuser -m alex`

---

**Q17.** `last` command kya dikhata hai?

- A) Last installed package
- B) Login/logout history — kaun kab login/logout hua
- C) Last modified files
- D) Last error message

---

**Q18.** Root user directly login karna zyada tar disable kyun rakha jaata hai production servers pe?

- A) Root slow hota hai
- B) Root koi bhi kaam kar sakta hai — galti se ya hacking se poora system destroy ho sakta hai
- C) Root sirf local machine pe kaam karta hai
- D) Root ka password yaad nahi rehta

---

## 🎯 Bonus (5 points each)

---

**Q19.** Ek command batao jo ek saath naya user banaye, home folder create kare, bash shell assign kare, aur sudo group mein add kare:

- A) `sudo useradd -m -s /bin/bash -G sudo newuser`
- B) `sudo adduser --sudo newuser`
- C) `sudo newuser -mG sudo`
- D) `sudo createuser -bash -sudo newuser`

---

**Q20.** `/etc/shadow` file kya hoti hai aur kise access milta hai?

- A) Normal file hai, sabko read access
- B) Users ke **encrypted passwords** hote hain — sirf root ya shadow group read kar sakta hai
- C) System shadows (backups) hote hain
- D) Hidden files ki list hoti hai

---

---

## ✅ ANSWERS

<details>
<summary>👆 Click karke Answers dekho — pehle khud try karo!</summary>

| Q# | Answer | Explanation |
|----|--------|-------------|
| Q1 | **B** | `whoami` = "Main kaun hoon?" — current username print karta hai |
| Q2 | **C** | `root` = Linux ka superuser — UID 0, unlimited powers |
| Q3 | **D** | `useradd` (low-level) aur `adduser` (interactive, Ubuntu) dono kaam karte hain |
| Q4 | **B** | `passwd` = password set/change karo. Apna: `passwd`, doosre ka: `sudo passwd username` |
| Q5 | **B** | sudo = **S**uper **U**ser **Do** — ek command root ki tarah chalao |
| Q6 | **B** | `/etc/passwd` mein user info hai — but passwords nahi! Passwords `/etc/shadow` mein hain |
| Q7 | **B** | `usermod -aG sudo rahul` — `-a`=append, `-G`=groups |
| Q8 | **B** | `-a` (append) ke bina `-G` purane groups replace kar deta hai! Bahut dangerous! |
| Q9 | **B** | `su -` = full login shell (priya ka PATH, variables sab load), `su` = sirf user switch |
| Q10 | **B** | `userdel -r` = user + home folder dono delete. Bina `-r` ke home folder reh jaata hai |
| Q11 | **A** | Format: `username:x:UID:GID:GECOS:home_dir:shell` — `x` ka matlab password `/etc/shadow` mein hai |
| Q12 | **B** | Priya ko `developers` group mein add karo — tab `/var/www/html` pe group access milega |
| Q13 | **A** | `uid` = user ID, `gid` = primary group ID, `groups` = sab groups |
| Q14 | **B** | `passwd -l` = lock (disable login). `passwd -u` = unlock |
| Q15 | **B** | `w` = who is logged in + kya kar rahe hain (CPU, command sab dikhata hai) |
| Q16 | **B** | `-m` = home banao, `-s /bin/bash` = bash shell, phir password set, phir groups add |
| Q17 | **B** | `last` = login history. `lastb` = failed login attempts |
| Q18 | **B** | Root se galti = poora system destroy. Isliye normal user + sudo better practice hai |
| Q19 | **A** | `useradd -m -s /bin/bash -G sudo newuser` — ek hi command mein sab! |
| Q20 | **B** | `/etc/shadow` = encrypted passwords — `ls -la /etc/shadow` chalao, `-rw-r-----` dikhega |

</details>

---

## 📊 Score Calculator

| Score | Result |
|-------|--------|
| 52-60 | 🏆 **User Management Expert!** |
| 39-51 | 🥈 **Good!** Concepts clear hain |
| 26-38 | 🥉 **Practice karo** |
| 0-25  | 📖 **DAY-6.md dobara padho** |

**Total Marks:** 60

---

## 💻 Practical Challenge

```bash
# 1. Apni user info dekho
whoami && id && groups

# 2. Test user banao
sudo useradd -m -s /bin/bash testuser
sudo passwd testuser        # Password set karo

# 3. User verify karo
cat /etc/passwd | grep testuser
ls /home/testuser

# 4. Group banao aur add karo
sudo groupadd testgroup
sudo usermod -aG testgroup testuser
id testuser                 # Groups dikhenge

# 5. Switch karo
su - testuser
whoami                      # testuser!
groups                      # testgroup dikhega
exit

# 6. Cleanup
sudo userdel -r testuser
sudo groupdel testgroup
```

---
**Quiz:** Day 6/30 | **Total Marks:** 60 | **Topic:** Users & Groups
