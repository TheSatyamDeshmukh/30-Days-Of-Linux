# Day 9 📝 — Text Processing

> **"Linux mein text processing = superpower! Lakhon lines ek second mein!"**

---

## 🌊 Pipe (`|`) — Commands Ko Joorna

Pipe sabse important concept hai aaj ka. Ek command ka output doosre command ka input ban jaata hai!

```
Command1 | Command2 | Command3
   ↓           ↓           ↓
Output1 → Input2 → Output2 → Input3 → Output3
```

**Analogy:** Assembly line factory jaisi! Ek machine ka product doosri machine mein jaata hai.

```bash
ls -l | grep ".txt"        # ls ka output grep ko do
cat file.txt | sort        # File ko sort karo
ps aux | grep firefox      # Firefox process dhundho
```

---

## 🔍 `grep` — Text Dhundhna

**Full Name:** Global Regular Expression Print

```bash
grep "word" file.txt              # File mein "word" wali lines dikhao
grep -i "word" file.txt           # Case-insensitive (WORD, Word, word sab)
grep -v "word" file.txt           # "word" NAHI wali lines
grep -n "word" file.txt           # Line number ke saath
grep -c "word" file.txt           # Kitni lines mein mila — count karo
grep -r "word" folder/            # Folder mein sab files mein dhundho
grep -l "word" folder/            # Sirf file names jisme mila
grep -w "word" file.txt           # Exact word match (partial nahi)
grep "^Start" file.txt            # "Start" se shuru hone wali lines
grep "end$" file.txt              # "end" pe khatam hone wali lines
```

**Real Examples:**
```bash
grep "error" /var/log/syslog      # Log mein errors dhundho
grep -r "TODO" ~/projects/        # Sab projects mein TODO dhundho
ps aux | grep python              # Python chal raha hai?
history | grep "apt install"      # Kya kya install kiya?
```

---

## 🔃 `sort` — Sort Karo

```bash
sort file.txt                     # Alphabetically sort karo
sort -r file.txt                  # Ulta (reverse) sort
sort -n numbers.txt               # Numbers se sort (numeric)
sort -k2 file.txt                 # 2nd column se sort karo
sort -u file.txt                  # Unique — duplicates hatao
sort file.txt | uniq              # Alternate tarika duplicates hatane ka
```

---

## 🎯 `uniq` — Duplicates Hatao

```bash
uniq file.txt                     # Consecutive duplicates hatao
sort file.txt | uniq              # Pehle sort karo phir unique karo
uniq -c file.txt                  # Har line kitni baar aayi — count
uniq -d file.txt                  # Sirf duplicate lines dikhao
uniq -u file.txt                  # Sirf unique lines dikhao
```

---

## ✂️ `cut` — Column Nikalo

```bash
cut -d',' -f1 file.csv            # CSV ka 1st column
cut -d',' -f1,3 file.csv          # 1st aur 3rd column
cut -d':' -f1 /etc/passwd         # : se split, 1st field (usernames!)
cut -c1-5 file.txt                # Characters 1 se 5 tak
```

**Example:**
```bash
# /etc/passwd mein se sirf usernames nikalo:
cut -d: -f1 /etc/passwd
```

---

## 📊 `wc` — Count Karo

**Full Name:** Word Count

```bash
wc file.txt                       # Lines, words, characters sab
wc -l file.txt                    # Sirf lines count karo
wc -w file.txt                    # Sirf words count karo
wc -c file.txt                    # Sirf characters count karo
ls | wc -l                        # Folder mein kitni files hain?
grep "error" log.txt | wc -l      # Kitne errors hain?
```

---

## 🔄 `sed` — Find & Replace

**Full Name:** Stream Editor

```bash
sed 's/old/new/' file.txt         # Har line mein pehla "old" → "new"
sed 's/old/new/g' file.txt        # Sab "old" → "new" (g = global)
sed 's/old/new/gi' file.txt       # Case-insensitive replace
sed -i 's/old/new/g' file.txt     # FILE mein seedha replace karo (-i = in-place)
sed '3d' file.txt                 # 3rd line delete karo
sed '1,5d' file.txt               # Lines 1 to 5 delete karo
sed -n '5,10p' file.txt           # Sirf lines 5 to 10 print karo
sed '/pattern/d' file.txt         # Pattern wali lines delete karo
```

**Real Example:**
```bash
# Config file mein IP address badlo:
sed -i 's/192.168.1.1/10.0.0.1/g' config.txt
```

---

## 🦅 `awk` — Advanced Text Processing

`awk` bahut powerful hai — columns, calculations, conditional logic sab!

```bash
awk '{print $1}' file.txt         # Pehla column print karo
awk '{print $1, $3}' file.txt     # 1st aur 3rd column
awk '{print NR, $0}' file.txt     # Line number ke saath
awk 'NR==5' file.txt              # Sirf 5th line
awk 'NR>=3 && NR<=7' file.txt     # Lines 3 to 7
awk -F',' '{print $2}' file.csv   # CSV ka 2nd column
awk '{sum += $1} END {print sum}' numbers.txt  # Column ka sum!
awk '/error/ {print}' log.txt     # Error wali lines print karo
```

**`/etc/passwd` Se Usernames + Home Folder:**
```bash
awk -F: '{print $1, $6}' /etc/passwd
```

---

## 🔀 `tr` — Characters Replace Karo

```bash
tr 'a-z' 'A-Z' < file.txt        # Lowercase → Uppercase
tr -d '\n' < file.txt             # Newlines delete karo
tr -s ' ' < file.txt             # Multiple spaces → single space
echo "hello" | tr 'a-z' 'A-Z'    # HELLO
```

---

## 🏋️ Practice — Real World Scenarios

```bash
# Scenario 1: Log file mein errors dhundho
echo -e "INFO: start\nERROR: failed\nINFO: ok\nERROR: crash" > test.log
grep "ERROR" test.log
grep -c "ERROR" test.log          # Kitne errors?

# Scenario 2: CSV se data nikalo
echo -e "Rahul,25,Delhi\nPriya,22,Mumbai\nRaj,28,Chennai" > data.csv
cut -d',' -f1 data.csv            # Sirf names
awk -F',' '{print $1, "age:", $2}' data.csv

# Scenario 3: Usernames list
cut -d: -f1 /etc/passwd | sort

# Scenario 4: Disk space — sirf important lines
df -h | grep -v tmpfs | grep -v udev

# Scenario 5: Word count
echo "Linux is amazing and Linux is free" > test.txt
wc -w test.txt                    # Words count karo
grep -o "Linux" test.txt | wc -l  # "Linux" kitni baar aaya?
```

---

## 📝 Aaj Ka Summary

✅ `|` Pipe — commands ko chain mein jodte hain
✅ `grep` — text dhundhna (sabse zyada use hone wala!)
✅ `sort` — sort karna
✅ `uniq` — duplicates hatana
✅ `cut` — columns nikalna
✅ `wc` — count karna
✅ `sed` — find & replace
✅ `awk` — advanced processing

---
**Day:** 9/30 | **Topic:** Text Processing | **Difficulty:** ⭐⭐⭐⭐☆
