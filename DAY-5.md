# Day 5 ✏️ — Text Editors: Vim & Nano

> **"Vim se bahar aana seekh lo — baaki sab baad mein!"** 😄

---

## 🤔 Terminal Mein Text Editor Kyun?

GUI mein Notepad ya VS Code use karte ho. Lekin server pe GUI nahi hota! **Sirf terminal hota hai.** Isliye terminal mein text editor aana chahiye — yeh ek **zaroorat** hai, choice nahi!

---

## 🟢 NANO — Beginner Ka Dost (Easy!)

Nano **simple aur easy** hai. Bilkul Notepad jaisa feel.

### Nano Kaise Kholte Hain:
```bash
nano filename.txt          # File kholo (nahi hai toh bana dega)
nano                       # Khali editor kholo
```

### Nano Ka Interface:
```
  GNU nano 6.2    notes.txt

Yahan type karo...
_

^G Help    ^O Save    ^X Exit    ^K Cut    ^U Paste
^W Search  ^R Read    ^J Justify ^C Cursor ^\ Replace
```

**`^` matlab `Ctrl` key!**

### Nano Shortcuts:

| Shortcut | Kaam |
|----------|------|
| `Ctrl + O` | **Save** karo (O = Write Out) |
| `Ctrl + X` | **Exit** karo |
| `Ctrl + W` | **Search** karo |
| `Ctrl + K` | Line **cut** karo |
| `Ctrl + U` | **Paste** karo |
| `Ctrl + G` | **Help** dekho |
| `Ctrl + C` | Cursor ka position dekho |
| `Alt + U` | **Undo** |

### Nano Practice:
```bash
nano mynotes.txt
# Type karo: "Aaj maine nano seekha!"
# Ctrl+O dabao → Enter dabao (save)
# Ctrl+X dabao (exit)
cat mynotes.txt            # Confirm karo — likha gaya?
```

---

## 🔴 VIM — Powerful Editor (Thoda Mushkil, Par Zaroori!)

Vim bahut powerful hai — **sab developers use karte hain.** Thoda time lagta hai seekhne mein, par ek baar seekh liya toh bohot fast kaam karte ho!

### Vim Kaise Kholte Hain:
```bash
vim filename.txt
vi filename.txt            # Older version (bhi kaam karta hai)
```

### ⚠️ SABSE PEHLE YEH YAAD KARO!

```
VIM SE BAHAR KAISE NIKALEIN:

Esc dabao → :q! type karo → Enter dabao

Yeh hai EMERGENCY EXIT! Kuch bhi ho jaaye — Esc phir :q!
```

---

### 🗺️ Vim Ke Modes — Sabse Zaroori Concept!

Vim mein **modes** hote hain — yeh concept hi Vim ko alag banata hai:

```
┌─────────────────┐         i, a, o          ┌─────────────────┐
│                 │ ─────────────────────────▶ │                 │
│   NORMAL MODE   │                            │   INSERT MODE   │
│  (default mode) │ ◀───────────────────────── │  (typing mode)  │
│                 │           Esc              │                 │
└─────────────────┘                            └─────────────────┘
        │                                              
        │ :                                            
        ▼                                              
┌─────────────────┐
│  COMMAND MODE   │
│  (:w, :q, etc.) │
└─────────────────┘
```

**Normal Mode** = Default. Yahan type karne se kuch nahi hota — commands chalte hain.
**Insert Mode** = Yahan actually type karte ho text.
**Command Mode** = Save, quit, search ke liye.

---

### 📝 INSERT MODE Mein Jaana

Normal mode se:

| Key | Kahan Insert Hoga |
|-----|-------------------|
| `i` | Cursor ke **pehle** |
| `a` | Cursor ke **baad** |
| `o` | Neeche **naya line** bana ke |
| `O` | Upar **naya line** bana ke |
| `I` | Line ke **bilkul shuru** mein |
| `A` | Line ke **bilkul end** mein |

---

### 🧭 NORMAL MODE — Navigate Karo

```bash
h    # ← Left
j    # ↓ Down
k    # ↑ Up
l    # → Right

w    # Agle word pe jaao
b    # Pichle word pe jaao
0    # Line ke shuru mein
$    # Line ke end mein
gg   # File ke bilkul shuru mein
G    # File ke bilkul ant mein
5G   # Line number 5 pe jaao
```

---

### ✂️ NORMAL MODE — Edit Karo

```bash
x       # Ek character delete
dd      # Poori line delete
5dd     # 5 lines delete
yy      # Line copy karo (yank)
5yy     # 5 lines copy
p       # Paste karo (neeche)
P       # Paste karo (upar)
u       # Undo (Ctrl+Z jaisa!)
Ctrl+r  # Redo
r       # Ek character replace karo
cw      # Word delete + insert mode
```

---

### 🔍 SEARCH Karna

```bash
/word       # "word" dhundho (n = next, N = previous)
?word       # Ulta dhundho
:%s/old/new/g    # Poori file mein "old" ko "new" se replace karo
```

---

### 💾 COMMAND MODE — Save & Quit

```bash
:w          # Save karo
:q          # Quit karo (changes nahi hone chahiye)
:wq         # Save + Quit
:q!         # Bina save ke FORCE quit ⚠️
:wq!        # Force save + quit
:x          # Save + quit (shortcut)
ZZ          # Save + quit (Normal mode mein)
```

---

### 🏃 Vim Quick Start — Step by Step

```bash
# 1. File kholo
vim test.txt

# 2. Insert mode mein jao
i

# 3. Kuch type karo
Linux seekhna maza aa raha hai!

# 4. Normal mode mein wapas jao
Esc

# 5. Save karo
:w

# 6. Quit karo
:q

# Ya dono ek saath
:wq
```

---

## 🆚 Nano vs Vim

| Feature | Nano | Vim |
|---------|------|-----|
| Seekhna | ⭐ Easy | ⭐⭐⭐ Mushkil |
| Speed | Normal | Bahut Fast |
| Features | Basic | Bahut Zyada |
| Servers pe | Milta hai | Hamesha milta hai |
| Professionals | Thoda kam | Zyada use karte hain |

> 💡 **Suggestion:** Pehle Nano seekho daily use ke liye. Vim thoda thoda practice karo — ek din kaam aayega!

---

## 🎮 Vim Practice Game

```bash
vimtutor       # Official Vim tutorial — 30 min mein basics!
```

---

## 🏋️ Practice

```bash
# Nano se
nano shopping.txt
# "Sabzi, Doodh, Bread" likho
# Save karo (Ctrl+O) aur exit karo (Ctrl+X)
cat shopping.txt

# Vim se
vim poem.txt
# i dabao
# "Linux mera dost hai" likho
# Esc dabao
# :wq dabao
cat poem.txt
```

---

## 📝 Aaj Ka Summary

✅ **Nano** — easy editor, beginners ke liye
✅ **Vim** — powerful editor, `i` se insert, `Esc` se normal, `:wq` se save+quit
✅ Vim Emergency Exit: `Esc` → `:q!` → Enter

---
**Day:** 5/30 | **Topic:** Text Editors | **Difficulty:** ⭐⭐⭐☆☆
