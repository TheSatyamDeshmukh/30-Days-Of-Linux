# 📝 Day 9 Quiz — Text Processing

> **Tip:** Ek test file banao `echo -e "apple\nbanana\napple\ncherry" > fruits.txt` aur commands try karo! 📝

---

## 🟢 Section A — Easy (1 point each)

---

**Q1.** `grep` command kisliye use hota hai?

- A) Files delete karne ke liye
- B) Text mein pattern/word dhundhne ke liye
- C) Files compress karne ke liye
- D) Processes kill karne ke liye

---

**Q2.** Pipe `|` ka kya kaam hai?

- A) File ko pipe (tube) mein copy karta hai
- B) Ek command ka output doosre command ka input ban jaata hai
- C) Files merge karta hai
- D) Terminal mein vertical line draw karta hai

---

**Q3.** `sort file.txt` kya karta hai?

- A) File delete karta hai
- B) File ki lines alphabetically sort karke dikhata hai
- C) File ko compress karta hai
- D) File ka size dikhata hai

---

**Q4.** `wc -l file.txt` kya count karta hai?

- A) Words
- B) Characters
- C) Lines
- D) File size

---

**Q5.** `uniq` command kya karta hai?

- A) Unique files dhundhta hai
- B) Consecutive duplicate lines hatata hai
- C) Files rename karta hai
- D) Unique permissions set karta hai

---

## 🟡 Section B — Medium (2 points each)

---

**Q6.** `grep -i "error" log.txt` mein `-i` flag ka kya matlab hai?

- A) Ignore the file
- B) Case-insensitive search — ERROR, Error, error sab match honge
- C) Invert match
- D) Include hidden files

---

**Q7.** `grep -v "DEBUG" app.log` kya karta hai?

- A) Sirf DEBUG wali lines dikhata hai
- B) DEBUG wali lines NAHI dikhata — baaki sab dikhata hai
- C) DEBUG word delete karta hai
- D) DEBUG wali lines count karta hai

---

**Q8.** `sed 's/old/new/g' file.txt` mein `/g` ka kya matlab hai?

- A) Generate new file
- B) Grep mode
- C) Global — har line mein sab occurrences replace karo (bina `g` ke sirf pehla)
- D) GUI mode

---

**Q9.** `cut -d',' -f2 data.csv` kya karta hai?

- A) CSV ki 2nd row nikalta hai
- B) CSV ko comma se split karke 2nd field (column) nikalta hai
- C) CSV delete karta hai
- D) CSV compress karta hai

---

**Q10.** `awk '{print $1}' file.txt` kya print karta hai?

- A) Poori file
- B) Pehla column (space se separated)
- C) Pehli line
- D) Pehla character

---

## 🔴 Section C — Output Predict Karo (3 points each)

**File `data.txt` ka content:**
```
banana
apple
cherry
apple
banana
apple
```

---

**Q11.** `sort data.txt` ka output kya hoga?

- A) banana, apple, cherry, apple, banana, apple (unchanged)
- B) apple, apple, apple, banana, banana, cherry
- C) cherry, banana, banana, apple, apple, apple
- D) Error

---

**Q12.** `sort data.txt | uniq` ka output kya hoga?

- A) banana, apple, cherry (original order)
- B) apple, banana, cherry (sorted + unique)
- C) apple, apple, apple, banana, banana, cherry
- D) cherry, banana, apple

---

**Q13.** `grep "apple" data.txt | wc -l` ka output kya hoga?

- A) 1
- B) 2
- C) 3
- D) 6

---

**Q14.** `sort data.txt | uniq -c` ka output mein `apple` ki line kaisi dikhegi?

- A) `apple`
- B) `1 apple`
- C) `3 apple`
- D) `apple 3`

---

**Q15.** `cat data.txt | sort | uniq | wc -l` ka output kya hoga?

- A) 6
- B) 3
- C) 1
- D) 0

---

## 🔴 Section D — Real World Commands (3 points each)

---

**Q16.** Log file mein sirf "ERROR" wali lines count karni hain. Sahi command?

- A) `count "ERROR" app.log`
- B) `grep "ERROR" app.log | wc -l`
- C) `wc -l "ERROR" app.log`
- D) `grep -c "ERROR" app.log` (Hint: dono sahi hain!)

---

**Q17.** `/etc/passwd` se sirf usernames (pehla column) nikalne ka command?

- A) `grep username /etc/passwd`
- B) `cut -d: -f1 /etc/passwd`
- C) `awk /etc/passwd`
- D) `sed /etc/passwd username`

---

**Q18.** File mein "linux" ko "Linux" se replace karna hai — file directly update ho (disk pe save):

- A) `sed 's/linux/Linux/g' file.txt`
- B) `sed -i 's/linux/Linux/g' file.txt`
- C) `replace linux Linux file.txt`
- D) `grep -r linux Linux file.txt`

---

## 🎯 Bonus — Pipe Chain (5 points each)

---

**Q19.** Sabse zyada CPU use karne wali top 3 processes dekhni hain. Sahi command?

- A) `ps aux | top 3`
- B) `ps aux --sort=-%cpu | head -4 | tail -3`
- C) `top -3`
- D) `ps aux | sort -k3 -rn | head -4`

---

**Q20.** `/var/log/auth.log` mein failed SSH login attempts count karne hain. Sahi command?

- A) `count failed /var/log/auth.log`
- B) `grep "Failed password" /var/log/auth.log | wc -l`
- C) `grep -failed /var/log/auth.log`
- D) `ssh --count-fails`

---

---

## ✅ ANSWERS

<details>
<summary>👆 Click karke Answers dekho!</summary>

| Q# | Answer | Explanation |
|----|--------|-------------|
| Q1 | **B** | `grep` = Global Regular Expression Print — pattern match karo |
| Q2 | **B** | `|` = pipe — `cmd1 | cmd2` — cmd1 ka stdout → cmd2 ka stdin |
| Q3 | **B** | `sort` = alphabetically sort karke stdout pe print karta hai (file change nahi hoti) |
| Q4 | **C** | `wc -l` = line count. `-w` = words, `-c` = characters |
| Q5 | **B** | `uniq` = consecutive duplicates hatao. `sort | uniq` = sab duplicates |
| Q6 | **B** | `-i` = case-insensitive. ERROR, error, Error sab match honge |
| Q7 | **B** | `-v` = invert match — matching lines EXCLUDE karo |
| Q8 | **C** | `g` = global flag. Bina `g` ke sirf har line ka pehla occurrence replace hoga |
| Q9 | **B** | `-d','` = delimiter comma, `-f2` = field/column 2 |
| Q10 | **B** | `$1` = first field (default delimiter = space/tab). `$2` = second field, etc. |
| Q11 | **B** | `sort` alphabetically: apple, apple, apple, banana, banana, cherry |
| Q12 | **B** | Sort phir uniq: apple, banana, cherry (3 unique values) |
| Q13 | **C** | File mein "apple" 3 baar hai (lines 2, 4, 6) |
| Q14 | **C** | `uniq -c` = count prefix. apple 3 baar = `      3 apple` |
| Q15 | **B** | 6 lines → sort → 6 lines → uniq → 3 unique → wc -l → **3** |
| Q16 | **B aur D** | Dono sahi hain! `grep "ERROR" | wc -l` aur `grep -c "ERROR"` same result dete hain |
| Q17 | **B** | `/etc/passwd` colon-separated hai. `-d:` = delimiter colon, `-f1` = first field |
| Q18 | **B** | `-i` = in-place edit — file seedha update hoti hai disk pe |
| Q19 | **D** | `sort -k3 -rn` = 3rd column (CPU%) se reverse numeric sort, `head -4` = header + top 3 |
| Q20 | **B** | `grep "Failed password"` specific string dhundhta hai auth.log mein, `wc -l` count karta hai |

</details>

---

## 📊 Score Calculator

| Score | Result |
|-------|--------|
| 52-62 | 🏆 **Text Processing Ninja!** |
| 39-51 | 🥈 **Good!** Pipe concepts clear hain |
| 26-38 | 🥉 **Practice karo** |
| 0-25  | 📖 **DAY-9.md dobara padho** |

**Total Marks:** 62

---

## 💻 Practical Challenge

```bash
# Setup — test file banao
cat > /tmp/testdata.txt << EOF
ERROR: Database connection failed
INFO: Server started
WARNING: Low disk space
ERROR: Authentication failed
INFO: User logged in
ERROR: Database connection failed
INFO: Backup completed
WARNING: High CPU usage
EOF

# 1. Sirf ERROR lines dekho
grep "ERROR" /tmp/testdata.txt

# 2. ERROR count karo
grep -c "ERROR" /tmp/testdata.txt

# 3. ERROR nahi wali lines
grep -v "ERROR" /tmp/testdata.txt

# 4. Sort karo
sort /tmp/testdata.txt

# 5. Unique lines
sort /tmp/testdata.txt | uniq

# 6. Har type kitni baar aaya?
sort /tmp/testdata.txt | uniq -c | sort -rn

# 7. Sirf log level nikalo (pehla word)
awk '{print $1}' /tmp/testdata.txt | sort | uniq -c

# Cleanup
rm /tmp/testdata.txt
```

---
**Quiz:** Day 9/30 | **Total Marks:** 62 | **Topic:** Text Processing
