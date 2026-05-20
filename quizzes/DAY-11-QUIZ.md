# 📝 Day 11 Quiz — Shell Scripting: Advanced

> **Tip:** Har script khud type karo aur chalao — copy-paste mat karo! 🚀

---

## 🟢 Section A — Easy (1 point each)

**Q1.** Function define karne ka sahi syntax kya hai?
- A) `function() { }` B) `myfunc() { commands; }` C) `def myfunc():` D) `func myfunc {}`

**Q2.** Script mein `$1` kya represent karta hai?
- A) Script ka naam B) Pehla argument C) Pehli line D) Process ID

**Q3.** Array banana ka sahi tarika?
- A) `arr = [1,2,3]` B) `arr=(1 2 3)` C) `arr{1,2,3}` D) `arr=[1 2 3]`

**Q4.** Array ka pehla element access karne ka tarika?
- A) `$arr[0]` B) `${arr[0]}` C) `arr[0]` D) `$arr(0)`

**Q5.** `set -e` script mein kya karta hai?
- A) Script encrypt karta hai B) Koi bhi command fail ho toh script band ho jaata hai C) Environment set karta hai D) Execution speed badhata hai

---

## 🟡 Section B — Medium (2 points each)

**Q6.** Yeh function kya return karega?
```bash
add() {
    local result=$(( $1 + $2 ))
    echo $result
}
val=$(add 5 3)
echo $val
```
- A) 0 B) 8 C) 53 D) Error

**Q7.** `local` keyword function mein kyun use karte hain?
- A) Location print karta hai B) Variable ko sirf function ke andar limit karta hai C) Local files access karta hai D) Loop banata hai

**Q8.** `$?` kya represent karta hai?
- A) Question mark character B) Pichle command ka exit code (0=success, non-0=error) C) All arguments D) Script ka naam

**Q9.** `trap "cleanup" EXIT` kya karta hai?
- A) Error trap karta hai B) Script exit hone pe "cleanup" function/command chalata hai C) EXIT command run karta hai D) Trap door banata hai

**Q10.** `case` statement mein `*)` ka kya matlab hai?
- A) Multiply B) Default case — koi aur match nahi hua toh C) All cases D) Error case

---

## 🔴 Section C — Hard (3 points each)

**Q11.** Yeh script kya output dega?
```bash
greet() {
    local msg="Hello $1"
    echo $msg
}
greet "Linux"
greet "World"
```
- A) `Hello Linux` sirf B) `Hello Linux` aur `Hello World` C) `Hello $1` D) Error

**Q12.** Array mein sab elements print karne ka sahi tarika?
- A) `echo $arr` B) `echo ${arr[@]}` C) `echo $arr[*]` D) `print arr`

**Q13.** Script ko arguments ke saath chalate ho: `./script.sh Delhi 25`. `$#` ki value kya hogi?
- A) 0 B) 1 C) 2 D) 3

**Q14.** `||` operator kab doosra command chalata hai?
- A) Pehla command successful ho B) Pehla command fail ho C) Hamesha D) Kabhi nahi

**Q15.** Kya galat hai?
```bash
myfunction {
    echo "Hello"
}
```
- A) `echo` galat hai B) `myfunction` ke baad `()` missing hai C) Kuch galat nahi D) Curly braces galat hain

---

## 🎯 Bonus (5 points each)

**Q16.** Script hai: `./backup.sh /home/rahul /backup/`. Script mein `$1` aur `$2` ki values kya hongi?
- A) `$1="/backup/"`, `$2="/home/rahul"` B) `$1="/home/rahul"`, `$2="/backup/"` C) Dono same D) Error

**Q17.** Error handling ke liye best practice script mein?
- A) Errors ignore karo B) `set -e` (exit on error) + `set -u` (undefined var error) + trap for cleanup C) Sirf echo se errors print karo D) try-catch use karo

---

## ✅ ANSWERS

<details>
<summary>👆 Answers dekho</summary>

| Q# | Answer | Explanation |
|----|--------|-------------|
| Q1 | B | `funcname() { commands; }` — standard bash function syntax |
| Q2 | B | `$1` = first argument. `$0`=script name, `$2`=second arg |
| Q3 | B | `arr=(item1 item2 item3)` — spaces se separate, parentheses mein |
| Q4 | B | `${arr[0]}` — curly braces zaroori hain arrays ke liye |
| Q5 | B | `set -e` = exit on error — professional scripts mein hamesha use karo |
| Q6 | B | `add 5 3` → `$(( 5 + 3 ))` = 8 → `echo 8` → `val=8` → `echo 8` |
| Q7 | B | `local` = variable function ke baad destroy ho jaata hai, global namespace pollute nahi hota |
| Q8 | B | `$?` = exit status. 0 = success, 1-255 = different errors |
| Q9 | B | `trap` = signal handler. EXIT signal pe cleanup run karo |
| Q10 | B | `*)` = wildcard — koi bhi value jo upar match nahi hui |
| Q11 | B | Function do baar call hua — dono baar alag argument ke saath |
| Q12 | B | `${arr[@]}` = sab elements. `[@]` = all indices |
| Q13 | C | 2 arguments diye — `Delhi` aur `25` |
| Q14 | B | `cmd1 || cmd2` — cmd1 fail (non-zero exit) toh cmd2 chalao |
| Q15 | B | Function syntax: `name() { }` — `()` zaroori hai |
| Q16 | B | Arguments order mein assign hote hain: `$1`=first, `$2`=second |
| Q17 | B | `set -e -u` + trap = professional error handling |

</details>

**Total Marks:** 50 | **Day:** 11/30 | **Topic:** Shell Scripting Advanced
