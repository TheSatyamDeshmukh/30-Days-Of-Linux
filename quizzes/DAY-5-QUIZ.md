# 📝 Day 5 Quiz — Text Editors: Vim & Nano

> **Yeh quiz try karne se pehle ek baar terminal mein `nano test.txt` aur `vim test.txt` kholo!**
> Practical experience ke baad quiz easy lagega! ✏️

---

## 🟢 Section A — Easy (1 point each)

---

**Q1.** Nano mein file save karne ka shortcut kya hai?

- A) `Ctrl + S`
- B) `Ctrl + O`
- C) `Ctrl + W`
- D) `Ctrl + X`

---

**Q2.** Nano mein editor se bahar nikalne ka shortcut kya hai?

- A) `Ctrl + Q`
- B) `Ctrl + O`
- C) `Ctrl + X`
- D) `Esc`

---

**Q3.** Vim mein "insert mode" mein jaane ke liye kaun si key dabate hain?

- A) `a`
- B) `i`
- C) `Insert`
- D) `e`

---

**Q4.** Vim mein "normal mode" mein wapas jaane ke liye kaun si key use hoti hai?

- A) `Enter`
- B) `Ctrl + C`
- C) `Esc`
- D) `q`

---

**Q5.** Vim mein file save karke quit karne ka command kya hai?

- A) `:exit`
- B) `:save`
- C) `:wq`
- D) `:sq`

---

## 🟡 Section B — Medium (2 points each)

---

**Q6.** Vim mein bina save kiye force quit karne ka command kya hai?

- A) `:q`
- B) `:quit`
- C) `:q!`
- D) `:exit!`

---

**Q7.** Nano mein `^` sign ka kya matlab hota hai shortcuts mein?

- A) Shift key
- B) Ctrl key
- C) Alt key
- D) Super key

---

**Q8.** Vim mein `dd` command kya karta hai?

- A) Double space add karta hai
- B) Poori line delete karta hai
- C) Document delete karta hai
- D) Default setting pe jaata hai

---

**Q9.** Vim mein `u` key ka kya kaam hai?

- A) Update karta hai
- B) Uppercase banata hai
- C) Undo karta hai (pichla kaam cancel)
- D) URL insert karta hai

---

**Q10.** Vim mein poori file mein "linux" ko "Linux" se replace karne ka command kya hai?

- A) `/linux/Linux`
- B) `:%s/linux/Linux/g`
- C) `:replace linux Linux`
- D) `s/linux/Linux/`

---

## 🔴 Section C — Vim Navigation (3 points each)

---

**Q11.** Vim mein Normal mode mein `gg` kya karta hai?

- A) Google search karta hai
- B) File ke bilkul shuru mein le jaata hai
- C) File ke end mein le jaata hai
- D) Ek page neeche jaata hai

---

**Q12.** Vim mein `G` (capital G) kya karta hai?

- A) File ke shuru mein jaata hai
- B) Grammar check karta hai
- C) File ke bilkul end mein le jaata hai
- D) Group mein jaata hai

---

**Q13.** Vim mein Normal mode mein `5dd` kya karta hai?

- A) 5 words delete karta hai
- B) 5 lines delete karta hai
- C) 5 characters delete karta hai
- D) File ko 5 baar copy karta hai

---

**Q14.** Vim mein `/word` type karne ke baad `n` key kya karta hai?

- A) Naya file kholata hai
- B) Agle match pe le jaata hai
- C) Search cancel karta hai
- D) Word ko replace karta hai

---

**Q15.** Vim mein cursor left, down, up, right move karne ke liye Normal mode mein kaun si keys use hoti hain?

- A) `w`, `s`, `a`, `d`
- B) Arrow keys only
- C) `h`, `j`, `k`, `l`
- D) `a`, `b`, `c`, `d`

---

## 🔴 Section D — Practical Scenarios (3 points each)

---

**Q16.** Tumne `vim important.txt` khola, bahut saari changes ki, aur ab realise hua ki sab galat tha. Sab changes discard karne hain. Kya karoge?

- A) `:wq` — changes save karke quit karo
- B) `:q` — normally quit karo
- C) `Esc` phir `:q!` — force quit bina save kiye
- D) Terminal band karo

---

**Q17.** Nano mein koi word dhundhna hai. Kaun sa shortcut use karoge?

- A) `Ctrl + F`
- B) `Ctrl + W`
- C) `Ctrl + S`
- D) `Ctrl + G`

---

**Q18.** Server pe sirf command line hai, GUI nahi. Ek config file edit karni hai. Kaun sa editor best choice hai?

- A) VS Code
- B) Notepad
- C) nano ya vim (dono terminal editors hain)
- D) gedit

---

**Q19.** Vim mein ek naya file khola. Kuch type karna hai. Steps kya hain (sahi order mein)?

- A) Seedha type karo
- B) `i` dabao → type karo → `Esc` dabao → `:wq` type karo
- C) `:insert` type karo → likho → `:save`
- D) `Ctrl + I` dabao → type karo → `Ctrl + S`

---

## 🎯 Bonus — Vim Emergency! (5 points)

**Q20.** Tumhara junior colleague pehli baar server pe kaam kar raha hai. Usne `vim /etc/nginx/nginx.conf` khola. Ab woh kuch bhi press karta hai — random characters file mein aa rahe hain! Woh panic mein hai. **File save nahi karni** — sab kuch as it was rakhna hai. Tumhe kya bataoge?

- A) "Computer restart karo"
- B) "`Ctrl + Z` dabao"
- C) "`Esc` dabao, phir `:q!` type karo aur `Enter` dabao — koi change save nahi hoga"
- D) "`:wq!` type karo"

---

---

## ✅ ANSWERS

<details>
<summary>👆 Click karo — Answers dekho</summary>

| Q# | Answer | Explanation |
|----|--------|-------------|
| Q1 | **B** | `Ctrl + O` = Write Out = Save. `Ctrl + S` nano mein kaam nahi karta! |
| Q2 | **C** | `Ctrl + X` = Exit nano. Agar unsaved changes hain toh save karne ka option dega |
| Q3 | **B** | `i` = insert mode — cursor ke pehle. `a` = append (baad mein), `o` = new line |
| Q4 | **C** | `Esc` = Normal mode mein wapas jao — Vim ka most important key! |
| Q5 | **C** | `:wq` = write (save) + quit. `:x` bhi same karta hai |
| Q6 | **C** | `:q!` = force quit — `!` matlab "mujhe pata hai, phir bhi karo!" |
| Q7 | **B** | `^` = Ctrl key. `^O` = `Ctrl + O`, `^X` = `Ctrl + X` |
| Q8 | **B** | `dd` = delete line — yank buffer mein jaati hai (paste kar sakte ho `p` se) |
| Q9 | **C** | `u` = undo — Windows mein `Ctrl + Z` ka vim equivalent |
| Q10 | **B** | `:%s/old/new/g` — `%` = poori file, `s` = substitute, `g` = global |
| Q11 | **B** | `gg` = go to beginning — file ka pehla character |
| Q12 | **C** | `G` (capital) = go to end — file ki aakhri line |
| Q13 | **B** | Number + command = repeat. `5dd` = 5 lines delete |
| Q14 | **B** | `n` = next match dhundho. `N` = previous match |
| Q15 | **C** | `h`=left, `j`=down, `k`=up, `l`=right — arrow keys bhi kaam karti hain par vim pros hjkl use karte hain! |
| Q16 | **C** | `Esc` pehle (normal mode), phir `:q!` (force quit without save) |
| Q17 | **B** | `Ctrl + W` = "Where is" = search in nano |
| Q18 | **C** | Server pe sirf terminal editors kaam karte hain — nano (easy) ya vim (powerful) |
| Q19 | **B** | Vim workflow: `i` (insert mode) → type karo → `Esc` (normal mode) → `:wq` (save+quit) |
| Q20 | **C** | `Esc` → `:q!` → `Enter` — Emergency exit! File unchanged rehti hai. Yeh sabse important vim tip hai! |

</details>

---

## 📊 Score Calculator

| Score | Result |
|-------|--------|
| 52-65 | 🏆 **Editor Expert!** Vim bhi seekh liya! |
| 39-51 | 🥈 **Good!** Nano toh pakka aa gaya |
| 26-38 | 🥉 **Practice karo** — editors daily use karo |
| 0-25  | 📖 **DAY-5.md dobara padho** |

**Total Marks:** 65 (Easy:5 + Medium:10 + Navigation:15 + Scenarios:12 + Bonus:5 + Practical:18)

---

## 💻 Practical Challenge

```bash
# Challenge 1: Nano se ek file banao
nano my_nano_file.txt
# "Nano seekh liya!" likho
# Ctrl+O → Enter (save)
# Ctrl+X (exit)
cat my_nano_file.txt       # Confirm karo

# Challenge 2: Vim mein file banao
vim my_vim_file.txt
# i dabao (insert mode)
# "Vim se darta tha, ab nahi!" likho
# Esc dabao
# :wq dabao
cat my_vim_file.txt        # Confirm karo

# Challenge 3: Vim mein replace karo
vim my_vim_file.txt
# Normal mode mein:
# :%s/darta/darta nahi/ dabao aur Enter
# :wq
cat my_vim_file.txt        # Changed!

# Cleanup
rm my_nano_file.txt my_vim_file.txt
```

---

## 🃏 Vim Cheatsheet — Quick Reference

```
MODES:
i      → Insert mode (type karo)
Esc    → Normal mode (navigate)
:      → Command mode (save/quit)

NAVIGATION (Normal mode):
gg     → File shuru
G      → File end
w      → Next word
b      → Prev word

EDITING (Normal mode):
dd     → Line delete
yy     → Line copy
p      → Paste
u      → Undo

SAVE/QUIT:
:w     → Save
:q     → Quit
:wq    → Save + Quit
:q!    → FORCE QUIT (no save) ← EMERGENCY EXIT!
```

---

*"Vim seekhne mein 1 ghanta, master karne mein 1 saal — par ek baar aa gayi toh superpower hai!"* ⚡

---
**Quiz:** Day 5/30 | **Total Marks:** 65 | **Topic:** Text Editors
