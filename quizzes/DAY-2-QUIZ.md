# 📝 Day 2 Quiz — Terminal & Basic Commands

> **Instructions:** Pehle khud socho, phir answers check karo!
> Practical tip: Quiz dene ke saath terminal mein commands try karte jao! 💻

---

## 🟢 Section A — Easy (1 point each)

---

**Q1.** Terminal mein `pwd` command kya karta hai?

- A) Password set karta hai
- B) Current directory ka path dikhata hai
- C) Files delete karta hai
- D) Program chalata hai

---

**Q2.** `ls` command ka kya kaam hai?

- A) Files list karta hai
- B) Linux start karta hai
- C) Location save karta hai
- D) Log files dikhata hai

---

**Q3.** Naya folder banane ke liye kaun sa command use karte hain?

- A) `newfolder`
- B) `touch`
- C) `mkdir`
- D) `create`

---

**Q4.** `cd ..` command kya karta hai?

- A) Current directory delete karta hai
- B) Ek level upar (parent folder) mein jaata hai
- C) Computer restart karta hai
- D) CD/DVD chalata hai

---

**Q5.** Keyboard pe kaun sa shortcut terminal screen saaf karta hai?

- A) `Ctrl + X`
- B) `Ctrl + Z`
- C) `Ctrl + L`
- D) `Ctrl + S`

---

## 🟡 Section B — Medium (2 points each)

---

**Q6.** `ls -la` command mein `-la` flags ka kya matlab hai?

- A) Large files dikhao
- B) Linux admin mode
- C) Long format + All files (hidden bhi) dikhao
- D) Last accessed files dikhao

---

**Q7.** `touch notes.txt` command kya karta hai?

- A) notes.txt file ko print karta hai
- B) notes.txt naam ki ek nayi khali file banata hai
- C) notes.txt file ko delete karta hai
- D) notes.txt file ko open karta hai

---

**Q8.** `echo "Hello" > file.txt` aur `echo "Hello" >> file.txt` mein kya fark hai?

- A) Koi fark nahi
- B) `>` replace karta hai, `>>` add karta hai (append)
- C) `>>` replace karta hai, `>` add karta hai
- D) Dono same kaam karte hain

---

**Q9.** File copy karne ke liye kaun sa command use hota hai?

- A) `move`
- B) `duplicate`
- C) `cp`
- D) `copy`

---

**Q10.** `rm -r myfolder` command kya karta hai?

- A) Sirf folder delete karta hai
- B) Folder rename karta hai
- C) Folder aur uske andar sab kuch permanently delete karta hai
- D) Folder ko restore karta hai

---

## 🔴 Section C — Hard (3 points each)

---

**Q11.** Terminal mein yeh prompt dikhta hai: `rahul@ubuntu:~/Documents$`
Iska kya matlab hai?

- A) Username=ubuntu, Computer=rahul, Folder=Documents
- B) Username=rahul, Computer=ubuntu, Current folder=Documents (home ke andar)
- C) Folder=rahul, OS=ubuntu, User=Documents
- D) Koi matlab nahi, sirf decoration hai

---

**Q12.** Agar tum `/home/rahul/` mein ho aur `cd ../../etc` type karo, tum kahan pahunch jaoge?

- A) `/home/etc`
- B) `/rahul/etc`
- C) `/etc`
- D) Error aayega

---

**Q13.** `mv oldname.txt newname.txt` command kya karta hai?

- A) File copy karta hai
- B) File rename karta hai (move = rename bhi!)
- C) File delete karta hai
- D) Do files merge karta hai

---

**Q14.** Tab key ka kya fark padta hai terminal mein?

- A) Spaces insert karta hai
- B) Command autocomplete karta hai — adha naam likho, Tab dabao
- C) Terminal band karta hai
- D) Naya terminal tab kholata hai

---

**Q15.** Yeh commands chalane ke baad `notes.txt` mein kya hoga?
```bash
echo "Line 1" > notes.txt
echo "Line 2" > notes.txt
echo "Line 3" >> notes.txt
```

- A) Teen lines hongi: Line 1, Line 2, Line 3
- B) Sirf Line 1 hogi
- C) Do lines hongi: Line 2, Line 3
- D) File empty hogi

---

## 🔴 Section D — Command Output Predict Karo (3 points each)

---

**Q16.** Tum `/home/rahul` mein ho. Yeh commands chalate ho:
```bash
mkdir projects
cd projects
pwd
```
`pwd` kya output dega?

- A) `/home/rahul`
- B) `/projects`
- C) `/home/rahul/projects`
- D) `projects`

---

**Q17.** Kaun sa command `/etc` folder ki files dikhata hai bina wahan gaye?

- A) `ls /etc`
- B) `cd /etc && ls`
- C) `show /etc`
- D) `dir /etc`

---

**Q18.** `cat` command kisliye use hota hai?

- A) Cats (billi) ke baare mein jaankari
- B) File ka content terminal mein dikhata hai
- C) File compress karta hai
- D) File copy karta hai

---

## 🎯 Bonus — Terminal Detective (5 points)

**Q19.** Ek naya user hai jisne pehli baar terminal khola. Woh yeh commands chalata hai:

```bash
cd Desktop
mkdir MyFolder
cd MyFolder
touch file1.txt file2.txt
ls
```

`ls` command ke baad screen pe kya dikhega?

- A) `Desktop MyFolder`
- B) `file1.txt file2.txt`
- C) `MyFolder`
- D) Kuch nahi (empty folder)

---

---

## ✅ ANSWERS

<details>
<summary>👆 Click karo — Answers dekho</summary>

| Q# | Answer | Explanation |
|----|--------|-------------|
| Q1 | **B** | `pwd` = Print Working Directory — "Main kahan hoon?" |
| Q2 | **A** | `ls` = List — current folder ki files/folders dikhao |
| Q3 | **C** | `mkdir` = Make Directory — naya folder banao |
| Q4 | **B** | `cd ..` = ek level upar jao (parent folder mein) |
| Q5 | **C** | `Ctrl + L` = screen clear (`clear` type karna bhi same kaam karta hai) |
| Q6 | **C** | `-l` = long format (size, date dikhao), `-a` = all files (hidden bhi) |
| Q7 | **B** | `touch` ek nayi khali file banata hai |
| Q8 | **B** | `>` overwrite (purana data jaata hai!), `>>` append (add karta hai) |
| Q9 | **C** | `cp` = copy — `cp source dest` |
| Q10 | **C** | `rm -r` = recursive delete — folder aur andar sab permanently! No undo! |
| Q11 | **B** | Format: `username@computername:current_dir$` |
| Q12 | **C** | `/home/rahul` → `..` = `/home` → `..` = `/` → `etc` = `/etc` |
| Q13 | **B** | `mv` ek hi command se rename bhi karta hai aur move bhi! |
| Q14 | **B** | Tab = autocomplete — sabse useful shortcut! Zaroor use karo! |
| Q15 | **C** | Pehla `>` Line 1 likhta hai, doosra `>` replace karta hai Line 2 se, phir `>>` Line 3 add karta hai |
| Q16 | **C** | `/home/rahul/projects` — `mkdir` ne folder banaya, `cd` ne enter kiya |
| Q17 | **A** | `ls /path` se kisi bhi folder ki list dekh sakte ho wahan gaye bina |
| Q18 | **B** | `cat` = file ka poora content screen pe print karo |
| Q19 | **B** | `file1.txt file2.txt` — `touch` ne dono files `MyFolder` ke andar banaye, `ls` unhe dikhata hai |

</details>

---

## 📊 Score Calculator

| Score | Result |
|-------|--------|
| 40-47 | 🏆 **Terminal Master!** — Sab clear hai! |
| 30-39 | 🥈 **Good!** — Almost there! |
| 20-29 | 🥉 **Practice karo** — Commands practice karni hain |
| 0-19  | 📖 **DAY-2.md dobara padho** — Koi baat nahi! |

**Total Marks:** 47 (Easy:5 + Medium:10 + Hard:15 + Detective:12 + Bonus:5)

---

## 💻 Practical Challenge

Quiz ke baad yeh karke dekho — apne aap test karo:

```bash
# Challenge 1: Is folder structure banao
mkdir -p quiz_test/day2/practice
cd quiz_test/day2/practice
touch q1.txt q2.txt q3.txt
ls -la

# Challenge 2: Files mein content likho
echo "Mera pehla command!" > q1.txt
echo "Linux mast hai!" >> q1.txt
echo "Aur ek line" >> q1.txt
cat q1.txt          # Kitni lines hongi?

# Challenge 3: Cleanup karo
cd ../../..
rm -rf quiz_test
ls                  # Gone!
```

---

*"Commands yaad karne ka best tarika — roz use karo!"* 🚀

---
**Quiz:** Day 2/30 | **Total Marks:** 47 | **Topic:** Terminal & Basic Commands
