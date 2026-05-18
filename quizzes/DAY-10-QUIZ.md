# 📝 Day 10 Quiz — Shell Scripting: Basics

> **Tip:** Har question ke script ko terminal mein actually chalao — sirf padhne se nahi seekhoge! 🔧

---

## 🟢 Section A — Easy (1 point each)

---

**Q1.** Shell script ki pehli line kya honi chahiye?

- A) `# Shell Script`
- B) `#!/bin/bash`
- C) `bash start`
- D) `#!/usr/bin/script`

---

**Q2.** Variable banana ka sahi tarika kya hai?

- A) `naam = "Rahul"`
- B) `naam= "Rahul"`
- C) `naam="Rahul"`
- D) `$naam="Rahul"`

---

**Q3.** Variable ki value use karne ke liye kya lagana padta hai?

- A) `@naam`
- B) `#naam`
- C) `%naam`
- D) `$naam`

---

**Q4.** Script ko executable banane ka command kya hai?

- A) `chmod +r script.sh`
- B) `chmod +x script.sh`
- C) `execute script.sh`
- D) `bash -x script.sh`

---

**Q5.** Script chalane ka sahi tarika kya hai?

- A) `script.sh`
- B) `run script.sh`
- C) `./script.sh`
- D) `open script.sh`

---

## 🟡 Section B — Medium (2 points each)

---

**Q6.** `read -p "Naam batao: " naam` mein `-p` flag ka kya kaam hai?

- A) Password mode
- B) Prompt text dikhata hai same line pe
- C) Print mode
- D) Protected input

---

**Q7.** `result=$((10 + 5 * 2))` mein `result` ki value kya hogi?

- A) 30
- B) 20
- C) 15
- D) 25 (BODMAS follow karta hai! 5*2=10, 10+10=20)

---

**Q8.** If condition mein numbers compare karne ke liye `-ge` ka matlab kya hai?

- A) Greater Entry
- B) Greater than or Equal to
- C) General Expression
- D) Get Equal

---

**Q9.** Yeh code kya print karega?
```bash
x=5
if [ $x -gt 3 ]; then
    echo "Bada hai"
else
    echo "Chhota hai"
fi
```

- A) `Chhota hai`
- B) `Bada hai`
- C) Kuch nahi
- D) Error

---

**Q10.** `for i in {1..5}` loop kitni baar chalega?

- A) 1 baar
- B) 4 baar
- C) 5 baar
- D) 6 baar

---

## 🔴 Section C — Script Output Predict Karo (3 points each)

---

**Q11.** Yeh script kya print karega?
```bash
#!/bin/bash
naam="Linux"
version=22
echo "Hello $naam $version!"
```

- A) `Hello $naam $version!`
- B) `Hello Linux 22!`
- C) `Hello naam version!`
- D) Error

---

**Q12.** Yeh loop kya print karega?
```bash
for fruit in Apple Banana Cherry; do
    echo "Fruit: $fruit"
done
```

- A) Sirf `Fruit: Apple`
- B) Teen lines: `Fruit: Apple`, `Fruit: Banana`, `Fruit: Cherry`
- C) `Fruit: Apple Banana Cherry`
- D) Error

---

**Q13.** `$#` kya represent karta hai script mein?

- A) Script ka size
- B) Script ko diye gaye arguments ki count
- C) Script ka line number
- D) Special character `#`

---

**Q14.** Yeh code kya print karega?
```bash
x=10
y=3
echo $((x % y))
```

- A) 3
- B) 0
- C) 1
- D) 10

---

**Q15.** While loop kab band hogi?
```bash
count=1
while [ $count -le 3 ]; do
    echo $count
    count=$((count + 1))
done
```

- A) count = 2 hone pe
- B) count = 3 hone pe
- C) count = 4 hone pe (jab condition false ho)
- D) Kabhi nahi — infinite loop hai

---

## 🔴 Section D — Script Debugging (3 points each)

**Har script mein ek error hai — dhundho:**

---

**Q16.** Kya galat hai?
```bash
#!/bin/bash
naam = "Rahul"
echo "Hello $naam"
```

- A) `echo` command galat hai
- B) `=` ke aas paas spaces hain — `naam="Rahul"` hona chahiye
- C) `#!/bin/bash` missing hai
- D) `$naam` galat hai

---

**Q17.** Kya galat hai?
```bash
#!/bin/bash
read -p "Number do: " num
if [ num -gt 10 ]; then
    echo "Bada hai"
fi
```

- A) `read` command galat hai
- B) `if` syntax galat hai
- C) `$` missing hai — `[ $num -gt 10 ]` hona chahiye
- D) `echo` command galat hai

---

**Q18.** Kya galat hai?
```bash
#!/bin/bash
for i in 1 2 3
    echo "Number: $i"
done
```

- A) `echo` galat jagah hai
- B) `do` keyword missing hai — `for i in 1 2 3; do` hona chahiye
- C) `done` galat hai
- D) Kuch galat nahi

---

## 🎯 Bonus — Complete the Script (5 points each)

---

**Q19.** Yeh script ek calculator hai. `___` mein kya aayega?
```bash
#!/bin/bash
read -p "Pehla number: " a
read -p "Doosra number: " b
sum=___
echo "Jod: $sum"
```

- A) `$(a + b)`
- B) `$a + $b`
- C) `$((a + b))`
- D) `(($a + $b))`

---

**Q20.** Script mein user se naam lo aur check karo woh "admin" hai ya nahi:
```bash
read -p "Naam: " naam
if [ ___ ]; then
    echo "Welcome Admin!"
else
    echo "Normal user"
fi
```
`___` mein kya aayega?

- A) `$naam = "admin"`
- B) `$naam == admin`
- C) `"$naam" == "admin"`
- D) `naam -eq "admin"`

---

---

## ✅ ANSWERS

<details>
<summary>👆 Click karke Answers dekho!</summary>

| Q# | Answer | Explanation |
|----|--------|-------------|
| Q1 | **B** | `#!/bin/bash` = shebang line — OS ko batata hai kis interpreter se run karo |
| Q2 | **C** | `naam="Rahul"` — `=` ke aas paas BILKUL space nahi! Yeh common mistake hai |
| Q3 | **D** | `$naam` — `$` variable ki value access karta hai |
| Q4 | **B** | `chmod +x` = execute permission add karo |
| Q5 | **C** | `./script.sh` — `./` matlab "current directory mein" |
| Q6 | **B** | `-p "text"` = prompt text same line pe dikhao |
| Q7 | **B** | BODMAS: `5*2=10` pehle, phir `10+10=20` |
| Q8 | **B** | `-ge` = Greater than or Equal. `-gt`=greater, `-lt`=less, `-le`=less/equal, `-eq`=equal, `-ne`=not equal |
| Q9 | **B** | `5 -gt 3` = 5 > 3 = true → "Bada hai" |
| Q10 | **C** | `{1..5}` = 1,2,3,4,5 — 5 values = 5 iterations |
| Q11 | **B** | Variables `$naam` aur `$version` replace hoke `Hello Linux 22!` banta hai |
| Q12 | **B** | Loop har fruit ke liye ek baar chalta hai — 3 fruits = 3 lines |
| Q13 | **B** | `$#` = argument count. `$0`=script name, `$1`=first arg, `$@`=all args |
| Q14 | **C** | `%` = modulo (remainder). `10 % 3` = 1 (10 = 3*3 + 1) |
| Q15 | **C** | Loop chalti hai jab condition true ho. `count=4` pe `4 -le 3` = false → band |
| Q16 | **B** | Variable assignment mein spaces allowed nahi — `naam = "Rahul"` error dega |
| Q17 | **C** | `[ num -gt 10 ]` galat — `$` missing. Variables `$` se access hote hain |
| Q18 | **B** | `for` loop mein `do` keyword zaroori hai: `for i in 1 2 3; do` |
| Q19 | **C** | Arithmetic ke liye `$(( ))` use karte hain — `$((a + b))` |
| Q20 | **C** | String comparison: `"$naam" == "admin"` — quotes recommended hain spaces se bachne ke liye |

</details>

---

## 📊 Score Calculator

| Score | Result |
|-------|--------|
| 52-62 | 🏆 **Script Writer!** |
| 39-51 | 🥈 **Good!** |
| 26-38 | 🥉 **Practice karo** |
| 0-25  | 📖 **DAY-10.md dobara padho** |

**Total Marks:** 62

---

## 💻 Practical Challenge — Khud Ka Calculator Banao

```bash
nano calculator.sh
```

```bash
#!/bin/bash
echo "=== Simple Calculator ==="
read -p "Pehla number: " a
read -p "Doosra number: " b
read -p "Operation (+/-/*/÷): " op

case $op in
    +) echo "Result: $((a + b))" ;;
    -) echo "Result: $((a - b))" ;;
    \*) echo "Result: $((a * b))" ;;
    /) 
       if [ $b -eq 0 ]; then
           echo "Error: Zero se divide nahi kar sakte!"
       else
           echo "Result: $((a / b))"
       fi
       ;;
    *) echo "Invalid operation!" ;;
esac
```

```bash
chmod +x calculator.sh
./calculator.sh
```

---
**Quiz:** Day 10/30 | **Total Marks:** 62 | **Topic:** Shell Scripting Basics
