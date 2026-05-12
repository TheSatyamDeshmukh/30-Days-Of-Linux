# 📝 Day 4 Quiz — File Permissions

> **Permissions sabse confusing topic hai beginners ke liye — isiliye zyada practice zaroori hai!**
> Terminal mein `ls -la` chalao, output dekho, phir quiz do! 🔐

---

## 🟢 Section A — Easy (1 point each)

---

**Q1.** Linux permissions mein `r` ka kya matlab hai?

- A) Run
- B) Read
- C) Root
- D) Remove

---

**Q2.** `w` permission ka kya matlab hai?

- A) Write
- B) Web
- C) Window
- D) Wget

---

**Q3.** `x` permission kisliye hoti hai?

- A) Exit
- B) Extra
- C) Execute (chalana)
- D) Export

---

**Q4.** `chmod +x script.sh` kya karta hai?

- A) Script delete karta hai
- B) Script ko execute permission deta hai
- C) Script copy karta hai
- D) Script ko read-only banata hai

---

**Q5.** `ls -l` output mein `d` ka kya matlab hai?

- A) Deleted file
- B) Directory (folder)
- C) Document
- D) Default file

---

## 🟡 Section B — Number to Permission (2 points each)

---

**Q6.** Permission number `7` ka matlab kya hai?

- A) `r--`
- B) `rw-`
- C) `rwx`
- D) `r-x`

---

**Q7.** `chmod 644 file.txt` ke baad owner kya kar sakta hai?

- A) Sirf read kar sakta hai
- B) Read aur write kar sakta hai
- C) Read, write aur execute kar sakta hai
- D) Kuch nahi kar sakta

---

**Q8.** `r` = 4, `w` = 2, `x` = 1 ke hisaab se `rw-` ki value kya hogi?

- A) 5
- B) 6
- C) 7
- D) 3

---

**Q9.** `chmod 755 script.sh` mein "others" (baaki sab) ke liye kya permissions hain?

- A) `rwx`
- B) `rw-`
- C) `r-x`
- D) `r--`

---

**Q10.** `chown rahul:developers file.txt` kya karta hai?

- A) Sirf owner badlata hai
- B) Owner ko `rahul` aur group ko `developers` banata hai
- C) File ko rahul ke folder mein move karta hai
- D) File ka naam badlata hai

---

## 🔴 Section C — Permission Reading (3 points each)

---

**Q11.** `ls -l` output hai:
```
-rwxr-xr-- 1 rahul devs 1234 Jan 15 script.sh
```
Group ke liye kya permissions hain?

- A) `rwx`
- B) `r-x`
- C) `r--`
- D) `rw-`

---

**Q12.** Same output ke liye — "others" ke liye kya permissions hain?
```
-rwxr-xr-- 1 rahul devs 1234 Jan 15 script.sh
```

- A) `rwx`
- B) `r-x`
- C) `r--`
- D) `---`

---

**Q13.** Koi user `priya` hai jo na owner hai, na `devs` group mein. Woh `script.sh` pe kya kar sakti hai?
```
-rwxr-xr-- 1 rahul devs 1234 Jan 15 script.sh
```

- A) Read, write, execute — teeno
- B) Read aur execute
- C) Sirf read
- D) Kuch nahi

---

**Q14.** `chmod 600 secret.txt` ke baad file kaisi dikhegi `ls -l` mein?

- A) `-rwxrwxrwx`
- B) `-rw-r--r--`
- C) `-rw-------`
- D) `-r--------`

---

**Q15.** Tumhe ek script banana hai jo:
- Owner: read, write, execute kare
- Group: sirf read kare
- Others: kuch na kar sake

Kaun sa `chmod` number sahi hai?

- A) `chmod 744`
- B) `chmod 740`
- C) `chmod 777`
- D) `chmod 700`

---

## 🔴 Section D — Tricky Questions (3 points each)

---

**Q16.** Ek folder pe `x` permission nahi hai (other ke liye). Koi baahri user us folder mein `cd` kar sakta hai?

- A) Haan, kyunki folder hai file nahi
- B) Nahi, folder pe `x` permission = andar jaane ki permission
- C) Sirf agar root user ho
- D) Haan, agar `r` permission hai toh

---

**Q17.** `chmod -R 755 /home/rahul/projects` mein `-R` ka kya matlab hai?

- A) Root permissions deta hai
- B) Remove permissions karta hai
- C) Recursive — folder aur uske andar sab files/folders ko same permission deta hai
- D) Read-only mode

---

**Q18.** `sudo` ki zaroorat kab hoti hai `chown` ke saath?

- A) Kabhi nahi
- B) Hamesha
- C) Sirf jab root user ki files ho
- D) Jab doosre user ki files ka owner badalna ho

---

## 🎯 Bonus — Real World Scenario (5 points each)

---

**Q19.** Tumne ek bash script banaya. `./myscript.sh` chalate ho toh yeh error aata hai:
```
bash: ./myscript.sh: Permission denied
```
Kya galat hai aur kaise fix karoge?

- A) Script mein syntax error hai — dobara likho
- B) Script ko execute permission nahi hai — `chmod +x myscript.sh` chalao
- C) Root user banana padega
- D) Script ka naam galat hai

---

**Q20.** Tumhare paas ek private SSH key file hai. Security best practice ke hisaab se uski permission kya honi chahiye?

- A) `777` — sabko access
- B) `644` — owner read/write, baaki read only
- C) `600` — sirf owner read/write, koi nahi
- D) `755` — standard file permission

---

---

## ✅ ANSWERS

<details>
<summary>👆 Click karo — Answers dekho</summary>

| Q# | Answer | Explanation |
|----|--------|-------------|
| Q1 | **B** | `r` = Read — file padhne ki permission |
| Q2 | **A** | `w` = Write — file mein likhne ki permission |
| Q3 | **C** | `x` = Execute — file chalane ya folder mein jaane ki permission |
| Q4 | **B** | `chmod +x` = execute permission add karo (+x = add execute) |
| Q5 | **B** | `d` = directory (folder). `-` = regular file, `l` = symbolic link |
| Q6 | **C** | 7 = 4+2+1 = r+w+x = `rwx` — full permission! |
| Q7 | **B** | 644: owner=6(rw-), group=4(r--), others=4(r--). Owner rw = read+write |
| Q8 | **B** | rw- = 4+2+0 = **6** |
| Q9 | **C** | 755: owner=7(rwx), group=5(r-x), others=5(**r-x**) |
| Q10 | **B** | `chown owner:group` dono ek saath badalta hai |
| Q11 | **B** | Permission string: `-` `rwx` `r-x` `r--` — owner|group|others. Group = `r-x` |
| Q12 | **C** | Teen groups: owner=rwx, group=r-x, others=**r--** |
| Q13 | **C** | Priya "others" mein hai. Others ki permission = `r--` = sirf read |
| Q14 | **C** | 600 = 6(rw-) 0(---) 0(---) = `-rw-------` |
| Q15 | **B** | Owner=7(rwx), Group=4(r--), Others=0(---) = `740` |
| Q16 | **B** | Folder pe `x` = "enter" permission. Bina `x` ke `cd` nahi hoga! |
| Q17 | **C** | `-R` = Recursive — poore folder tree pe apply karta hai |
| Q18 | **D** | Apni files ka owner khud badal sakte ho, doosre ki ke liye sudo chahiye |
| Q19 | **B** | "Permission denied" = execute permission missing. `chmod +x` fix karta hai |
| Q20 | **C** | SSH private key = `600` — sirf owner padh sake. SSH khud bhi warn karta hai agar permissions loose hain! |

</details>

---

## 📊 Score Calculator

| Score | Result |
|-------|--------|
| 50-60 | 🏆 **Permission Guru!** Excellent! |
| 38-49 | 🥈 **Good!** Thoda aur practice |
| 25-37 | 🥉 **Average** — Numbers wala section dobara padho |
| 0-24  | 📖 **DAY-4.md se shuru karo** |

**Total Marks:** 60 (Easy:5 + Numbers:10 + Reading:15 + Tricky:9 + Bonus:10 + Practical:11)

---

## 💻 Practical Challenge — Permission Experiments

```bash
# Experiment 1: Permission change dekho
touch test.sh
ls -l test.sh              # -rw-r--r-- (no x)
chmod +x test.sh
ls -l test.sh              # -rwxr-xr-x (x add hua!)

# Experiment 2: Numbers se
touch secret.txt
chmod 600 secret.txt
ls -l secret.txt           # -rw------- dikhega

# Experiment 3: Script banao aur chalao
echo '#!/bin/bash' > hello.sh
echo 'echo "Hello! Permission kaam kar rahi hai!"' >> hello.sh
chmod +x hello.sh
./hello.sh                 # Chalega!

# Experiment 4: Permission hatao aur dekho
chmod -x hello.sh
./hello.sh                 # Permission denied!
chmod +x hello.sh          # Wapas do
./hello.sh                 # Phir chalega!

# Cleanup
rm test.sh secret.txt hello.sh
```

---

## 🧮 Permission Calculator — Yaad Rakhne Ka Tarika

```
rwx = 4+2+1 = 7  (full access)
rw- = 4+2+0 = 6  (read + write)
r-x = 4+0+1 = 5  (read + execute)
r-- = 4+0+0 = 4  (read only)
--- = 0+0+0 = 0  (no access)

Common combos:
755 = rwxr-xr-x  ← Scripts ke liye
644 = rw-r--r--  ← Normal files ke liye
600 = rw-------  ← Private files ke liye
700 = rwx------  ← Private scripts ke liye
```

---

*"Permissions yaad ho gayi toh Linux ka security system samajh gaya!"* 🔐

---
**Quiz:** Day 4/30 | **Total Marks:** 60 | **Topic:** File Permissions
