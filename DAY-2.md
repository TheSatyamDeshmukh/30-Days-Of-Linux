# Day 2 💻 — Terminal & Basic Commands

> **"Terminal se daro mat — yeh tumhara dost hai!"**

---

## 🖥️ Terminal Kya Hota Hai?

Terminal ek **black screen** hai jahan tum text type karke computer se baat karte ho.

**Real Life Analogy:** Socho tum ek restaurant mein ho. Tum:
- **Mouse + GUI** = Waiter ko bulao, menu dekho, point karke order karo
- **Terminal** = Seedha kitchen mein jao aur directly chef se bolo "1 burger chahiye!"

Terminal zyada **powerful** hai — seedha computer se baat karte ho!

---

## 🚀 Terminal Kaise Kholte Hain?

### Ubuntu Mein:
- **Shortcut:** `Ctrl + Alt + T` dabao — terminal khul jaayega!
- **Ya:** Applications → Search "Terminal"

### Pehli Baar Dekhoge Toh Yeh Dikhega:
```
username@computername:~$
```

**Iska Matlab:**
```
rahul @ my-laptop : ~ $
  ↑         ↑       ↑  ↑
User     Computer  Folder  Command
 Name      Name   (~ = home) likho yahan
```

---

## 📌 Aaj Ke Commands — Ek Ek Karke Seekho

---

### Command 1: `pwd` — Main Kahan Hoon?

**Full Name:** Print Working Directory
**Kaam:** Batata hai abhi tum computer mein KAHAN ho

```bash
pwd
```

**Output:**
```
/home/rahul
```

**Samajhne Ka Tarika:**
Socho computer ek **bada mall** hai. Mall mein hazaro dukane hain. `pwd` matlab — "Mall ke andar abhi main KIS DUKAN ke saamne hoon?"

```
/ (Root — Mall ka main gate)
├── home/
│   └── rahul/     ← TUM YAHAAN HO (pwd yahi batayega)
│       ├── Desktop/
│       ├── Documents/
│       └── Downloads/
├── etc/
└── var/
```

---

### Command 2: `ls` — Yahan Kya Kya Hai?

**Full Name:** List
**Kaam:** Current folder mein jo files/folders hain unhe dikhao

```bash
ls
```

**Output:**
```
Desktop  Documents  Downloads  Music  Pictures  Videos
```

**Extra Options (Flags):**

```bash
ls -l         # Detail mein dikhao (size, date, owner)
ls -a         # Hidden files bhi dikhao (jo . se shuru hoti hain)
ls -la        # Dono saath
ls -lh        # Size human readable mein (KB, MB)
ls /etc       # Kisi aur folder ki list dekho
```

**`ls -l` ka Output Samajhna:**
```
-rw-r--r-- 1 rahul rahul 1234 Jan 15 10:30 notes.txt
 ↑          ↑   ↑     ↑     ↑       ↑         ↑
Permission Links Owner Group Size   Date      Filename
```

**Samajhne Ka Tarika:**
`ls` waise hai jaise room ki light jalao — "Is room mein kya kya hai?" And `-l` matlab "thoda aur bata, sirf naam nahi!"

---

### Command 3: `cd` — Ek Jagah Se Doosri Jagah Jao

**Full Name:** Change Directory
**Kaam:** Ek folder se doosre folder mein jaana

```bash
cd Documents          # Documents folder mein jao
cd ..                 # Ek level UPAR jao
cd ../..              # Do level upar jao
cd ~                  # Seedha HOME folder mein jao
cd /                  # SABSE UPAR (root) mein jao
cd -                  # Pichle folder mein wapas jao
cd /home/rahul/Music  # Direct path se kahan bhi jao
```

**Practice Example:**
```bash
pwd                    # /home/rahul
cd Documents           # Documents mein gaye
pwd                    # /home/rahul/Documents ✅
cd ..                  # Ek level upar
pwd                    # /home/rahul ✅
cd /etc                # Seedha /etc mein gaye
pwd                    # /etc ✅
cd ~                   # Ghar wapas!
pwd                    # /home/rahul ✅
```

**Samajhne Ka Tarika:**
`cd` waise hai jaise ghar mein ek room se doosre room mein jaana. `cd ..` matlab "is room se bahar nikal ke pichle room mein jao!"

---

### Command 4: `mkdir` — Naya Folder Banao

**Full Name:** Make Directory
**Kaam:** Naya folder (directory) banana

```bash
mkdir myfolder                    # "myfolder" naam ka folder
mkdir "My Documents"              # Space wale naam ke liye quotes
mkdir folder1 folder2 folder3     # Ek saath kai folders
mkdir -p projects/linux/day1      # Nested folders (ek ke andar ek)
```

**`-p` Flag Ka Magic:**
```bash
mkdir -p a/b/c
# Yeh teen folders ek saath banata hai:
# a/
# a/b/
# a/b/c/
# Agar beech wala exist nahi karta tab bhi kaam karta hai!
```

---

### Command 5: `touch` — Khali File Banao

**Full Name:** Touch (literally — sirf file ko "touch" karo)
**Kaam:** Ek naya KHALI file banana

```bash
touch notes.txt                   # notes.txt banao
touch file1.txt file2.txt         # Ek saath kai files
touch index.html style.css        # Alag alag extensions
```

> 💡 **Note:** `touch` existing file pe chalao toh file ki date update hoti hai — delete nahi hoti!

---

### Command 6: `cat` — File Padho

**Full Name:** Concatenate
**Kaam:** File ka poora content screen pe dikhao

```bash
cat notes.txt                     # File padho
cat file1.txt file2.txt           # Do files ek saath padho
cat -n notes.txt                  # Line numbers ke saath
```

**Badi Files Ke Liye Alternatives:**
```bash
less notes.txt        # Page by page padho (q dabao bahar aane ke liye)
more notes.txt        # Less jaisa (older version)
head notes.txt        # Sirf pehli 10 lines
head -n 5 notes.txt   # Sirf pehli 5 lines
tail notes.txt        # Sirf aakhri 10 lines
tail -f log.txt       # Live dekhte raho (log files ke liye!)
```

---

### Command 7: `echo` — Kuch Print Karo / File Mein Likho

**Kaam:** Text print karo ya file mein save karo

```bash
echo "Hello Linux!"               # Screen pe print karo
echo "Meri notes" > notes.txt     # File BANAO aur likho (purana MITA dega!)
echo "Aur notes" >> notes.txt     # File mein ADD karo (purana REHTA hai!)
echo $HOME                        # Variable ki value print karo
```

**`>` vs `>>` — BAHUT ZAROORI FARK!**

```bash
echo "Line 1" > file.txt    # file.txt: "Line 1"
echo "Line 2" > file.txt    # file.txt: "Line 2" (Line 1 GAYI! ⚠️)

echo "Line 1" > file.txt    # file.txt: "Line 1"
echo "Line 2" >> file.txt   # file.txt: "Line 1\nLine 2" (DONO hain! ✅)
```

---

### Command 8: `cp` — Copy Karo

**Full Name:** Copy
**Kaam:** File ya folder copy karna

```bash
cp source.txt destination.txt         # File copy karo
cp notes.txt backup_notes.txt         # Backup banao
cp -r myfolder/ newfolder/            # Poora folder copy karo (-r = recursive)
cp file.txt /home/rahul/Documents/    # Doosri jagah copy karo
```

---

### Command 9: `mv` — Move Ya Rename Karo

**Full Name:** Move
**Kaam:** File move karna YA rename karna (dono kaam ek hi command!)

```bash
mv oldname.txt newname.txt               # RENAME karo
mv file.txt /home/rahul/Documents/       # MOVE karo
mv folder/ /tmp/                         # Folder move karo
mv file.txt /Documents/newname.txt       # Move + rename ek saath!
```

---

### Command 10: `rm` — Delete Karo

**Full Name:** Remove
**Kaam:** File ya folder delete karna

```bash
rm file.txt               # File delete karo
rm file1.txt file2.txt    # Kai files delete karo
rm -r myfolder/           # Folder aur sab kuch delete karo
rm -i file.txt            # Delete karne se pehle confirm maango (SAFE!)
rm -rf folder/            # Force delete — koi sawaal nahi (DANGEROUS! ⚠️)
```

> ⛔ **WARNING — BAHUT ZAROORI:**
> **Linux mein Recycle Bin NAHI hota!**
> `rm` se jo delete kiya — woh **SEEDHA GONE** hai, koi recovery nahi!
> Pehle soch lo, phir delete karo.
> `rm -rf /` kabhi mat chalana — poora system delete ho jaata hai!

---

## ⌨️ Keyboard Shortcuts — Terminal Ka GPS

| Shortcut | Kaam |
|----------|------|
| `Tab` | **Autocomplete** — adha naam likho, Tab dabao, poora ho jaata! |
| `↑` Arrow | Pichli command wapas laao |
| `↓` Arrow | Aagla command (history mein) |
| `Ctrl + C` | **Running command BAND karo** |
| `Ctrl + L` | Screen saaf karo (ya `clear` type karo) |
| `Ctrl + A` | Cursor line ke shuru mein |
| `Ctrl + E` | Cursor line ke end mein |
| `Ctrl + W` | Pichla word delete karo |
| `Ctrl + R` | Command history mein search karo |
| `Ctrl + D` | Terminal band karo (logout) |
| `q` | `less`/`man` se bahar niklo |

> 💡 **Tab Shortcut Sabse Important Hai!**
> `Docu` likh ke Tab dabao → `Documents` khud complete ho jaata!

---

## 🛤️ Path Types — Absolute vs Relative

### Absolute Path (Poora Address):
```bash
cd /home/rahul/Documents    # / se shuru — poora address
ls /etc/hosts               # Har jagah se kaam karta hai
```

### Relative Path (Current Location Se):
```bash
cd Documents                # Sirf naam — current location se jaata hai
ls ../Music                 # Pichle folder ka Music
```

**Analogy:**
- Absolute = "Delhi, Connaught Place, Block A, Shop 5" (koi bhi samajhe)
- Relative = "2 blocks aage, phir left" (tabhi kaam kare jab tum already wahan ho)

---

## 🏋️ Practice Exercise — Aaj Ka Kaam

Terminal kholo aur yeh sab karo:

```bash
# Step 1: Dekho kahan ho
pwd

# Step 2: Ek folder banao
mkdir linux-practice

# Step 3: Us folder mein jao
cd linux-practice

# Step 4: Kuch files banao
touch day1.txt day2.txt notes.txt

# Step 5: Files dekho
ls -la

# Step 6: File mein kuch likho
echo "Aaj maine Linux terminal seekha!" > day1.txt
echo "Bahut mast hai!" >> day1.txt

# Step 7: File padho
cat day1.txt

# Step 8: File copy karo
cp day1.txt day1_backup.txt

# Step 9: File rename karo
mv day2.txt second_day.txt

# Step 10: Sab dekho
ls -l

# Step 11: Wapas jao
cd ..

# Step 12: Banaya hua folder dekho
ls
```

---

## ❌ Common Galtiyan Aur Fix

| Galti | Error Message | Fix |
|-------|--------------|-----|
| `cd documents` (chhoti d) | `No such file or directory` | Linux case-sensitive! `cd Documents` |
| `rm -r myfolder` galat folder | Files gayi! | Pehle `ls` se confirm karo |
| Space wale folder mein jaana | `cd: too many arguments` | `cd "My Folder"` ya `cd My\ Folder` |

---

## 📝 Aaj Ka Summary

✅ `pwd` — Main kahan hoon
✅ `ls` — Kya kya hai yahan
✅ `cd` — Folder mein jaana/aana
✅ `mkdir` — Naya folder banana
✅ `touch` — Khali file banana
✅ `cat` — File padhna
✅ `echo` — File mein likhna
✅ `cp` — Copy karna
✅ `mv` — Move/Rename karna
✅ `rm` — Delete karna (dhyan se!)
✅ `Tab` — Autocomplete (SABSE USEFUL!)

---

## 📅 Kal Kya Seekhenge? (Day 3 Preview)

Kal hum **Linux ka File System** samjhenge — `/home`, `/etc`, `/var`, `/tmp` kya hote hain aur har jagah ka kya kaam hai!

---

*"Roz 10 commands — 30 din mein 300 commands! Tab Linux expert ho jaoge!"* 💪

---
**Day:** 2/30 | **Topic:** Terminal & Basic Commands | **Difficulty:** ⭐⭐☆☆☆
