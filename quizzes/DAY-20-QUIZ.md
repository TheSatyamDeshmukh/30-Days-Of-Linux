# 📝 Day 20 Quiz — Environment Variables

> **Tip:** `env` aur `echo $PATH` chalao terminal mein! 🌿

---

## 🟢 Section A — Easy (1 point each)

**Q1.** Environment variable dekhne ke liye?
- A) `var` B) `echo $VARIABLE_NAME` C) `show var` D) `get $var`

**Q2.** Sab environment variables list karne ka command?
- A) `list env` B) `env` C) `vars` D) `showenv`

**Q3.** `HOME` variable mein kya hota hai?
- A) Home page URL B) Tumhara home directory path C) Home network IP D) Hostname

**Q4.** Variable set karna (current session ke liye)?
- A) `set MY_VAR=hello` B) `export MY_VAR="hello"` C) `MY_VAR := hello` D) `define MY_VAR hello`

**Q5.** `.bashrc` file kab execute hoti hai?
- A) Sirf startup pe B) Har naye interactive bash session pe (terminal kholne pe) C) Sirf login pe D) Sirf logout pe

---

## 🟡 Section B — Medium (2 points each)

**Q6.** `PATH` variable kisliye hota hai?
- A) File ka path store karta hai B) Directories ki list jahan commands dhundhi jaati hain C) Network path D) User's path

**Q7.** `PATH` mein naya folder permanently add karne ke liye kahan likhte hain?
- A) `/etc/path` B) `~/.bashrc` mein `export PATH="$PATH:/new/folder"` C) `/bin/path` D) `~/.path`

**Q8.** `source ~/.bashrc` kya karta hai?
- A) Bashrc file delete karta hai B) Bashrc changes current session mein apply karta hai bina restart ke C) Bashrc backup karta hai D) Bash restart karta hai

**Q9.** `.bashrc` aur `.bash_profile` mein kya fark hai?
- A) Koi fark nahi B) `.bashrc` = interactive shells, `.bash_profile` = login shells C) Dono same time pe run hote hain D) `.bash_profile` newer hai

**Q10.** `PS1` variable kya control karta hai?
- A) Process status B) Terminal prompt ka format/appearance C) Password security D) Print settings

---

## 🔴 Section C — Hard (3 points each)

**Q11.** Script mein `export` ke bina variable define kiya. Child process use kar sakta hai?
- A) Haan, hamesha B) Nahi, `export` ke bina variable sirf current shell mein available hai C) Depends D) Haan, agar root hai

**Q12.** System-wide environment variables (sab users ke liye) kahan likhte hain?
- A) `~/.bashrc` B) `/etc/environment` C) `/root/.bashrc` D) `/etc/bash`

**Q13.** `MY_VAR="test" python3 script.py` kya karta hai?
- A) Error B) `MY_VAR` sirf us ek command ke liye set hota hai, global nahi C) Permanent variable banata hai D) Python mein variable inject karta hai

**Q14.** `unset MY_VAR` kya karta hai?
- A) Variable 0 pe set karta hai B) Variable ko environment se completely remove karta hai C) Variable lock karta hai D) Variable reset karta hai default pe

**Q15.** Colored terminal prompt banane ke liye PS1 mein kya use karte hain?
- A) HTML color codes B) ANSI escape codes jaise `\033[0;32m` C) CSS colors D) Hex colors directly

---

## 🎯 Bonus (5 points each)

**Q16.** Developer ne script likhi jo `JAVA_HOME` variable use karti hai. Production server pe run nahi ho rahi. Debug kaise?
- A) Script delete karo B) `echo $JAVA_HOME` → agar empty, `export JAVA_HOME=/path/to/java` → `/etc/environment` mein permanently add C) Java reinstall D) Server restart

**Q17.** Terminal prompt ko customize karna hai — `[rahul@ubuntu ~/projects]$` format mein. `PS1` kya hoga?
- A) `PS1="rahul@ubuntu"` B) `PS1="[\u@\h \w]\$ "` (\u=user, \h=hostname, \w=path) C) `PS1="{user}@{host}"` D) `PS1="$USER@$HOST"`

---

## ✅ ANSWERS

<details>
<summary>👆 Answers dekho</summary>

| Q# | Answer | Explanation |
|----|--------|-------------|
| Q1 | B | `echo $VARNAME` ya `printenv VARNAME` |
| Q2 | B | `env` ya `printenv` — sab current environment |
| Q3 | B | `HOME=/home/username` — tilde `~` iska shortcut hai |
| Q4 | B | `export` = variable ko child processes ke liye bhi available banao |
| Q5 | B | `.bashrc` = interactive non-login shells (new terminal window) |
| Q6 | B | PATH = directories separated by `:`. Command dhundhna = PATH mein ek ek folder check |
| Q7 | B | Permanent PATH update = `~/.bashrc` mein, then `source ~/.bashrc` |
| Q8 | B | `source` = current shell mein file execute karo (new shell nahi) |
| Q9 | B | `.bashrc` = every interactive shell, `.bash_profile` = login shell only |
| Q10 | B | PS1 = Prompt String 1 — terminal mein jo `$` se pehle dikhta hai |
| Q11 | B | Without `export`, variable = local to current shell only |
| Q12 | B | `/etc/environment` = system-wide, all users, all shells |
| Q13 | B | `VAR=val command` = temporary environment for that command only |
| Q14 | B | `unset` = completely remove from environment |
| Q15 | B | ANSI codes: `\033[0;32m` = green start, `\033[0m` = reset |
| Q16 | B | Diagnose (echo) → fix (export) → persist (/etc/environment) |
| Q17 | B | PS1 escape sequences: `\u`=username, `\h`=hostname, `\w`=working dir |

</details>

**Total Marks:** 50 | **Day:** 20/30 | **Topic:** Environment Variables
