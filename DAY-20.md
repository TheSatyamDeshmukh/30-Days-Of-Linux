# Day 20 🌿 — Environment Variables

> **"Environment variables = Linux ki secret settings!"**

---

## 🤔 Environment Variable Kya Hota Hai?

System ki **global settings** jo sab programs use karte hain. Jaise:
- `PATH` = Commands kahan se dhundhe jaayein?
- `HOME` = Tumhara home folder kahan hai?
- `USER` = Tumhara username kya hai?

---

## 👁️ Variables Dekhna

```bash
env                          # Sab environment variables
printenv                     # Same as env
printenv PATH                # Specific variable dekho
echo $PATH                   # $ se bhi dekh sakte ho
echo $HOME
echo $USER
echo $SHELL
echo $LANG
echo $PWD
```

---

## 📌 Important Variables

| Variable | Kya Hai |
|----------|---------|
| `PATH` | Directories jahan commands dhundhe jaate hain |
| `HOME` | Tumhara home directory |
| `USER` | Tumhara username |
| `SHELL` | Kaun sa shell use ho raha hai |
| `LANG` | Language setting |
| `EDITOR` | Default text editor |
| `TERM` | Terminal type |
| `PS1` | Terminal prompt ka format |

---

## ✏️ Variables Set Karna

```bash
# Temporary (sirf current session):
export MY_VAR="Hello Linux"
echo $MY_VAR

# Program ke liye temporary:
MY_VAR="test" python3 script.py

# Permanent banana:
nano ~/.bashrc
# Yeh line add karo:
export MY_VAR="Hello Linux"
export PATH="$PATH:/home/rahul/scripts"

# Changes apply karo:
source ~/.bashrc
# ya
. ~/.bashrc
```

---

## 🗂️ Config Files

```bash
~/.bashrc          # Har bash session pe run hota hai (interactive)
~/.bash_profile    # Login shell pe run hota hai
~/.profile         # Bash aur doosre shells ke liye
/etc/environment   # System-wide variables (sab users ke liye)
/etc/profile       # System-wide shell config
/etc/profile.d/    # Additional system configs
```

**Order:**
```
System boots → /etc/environment → /etc/profile → ~/.bash_profile → ~/.bashrc
```

---

## 🛣️ PATH — Bahut Zaroori!

```bash
echo $PATH
# /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

# PATH mein naya folder add karo:
export PATH="$PATH:/home/rahul/myscripts"

# Permanent add karo (bashrc mein):
echo 'export PATH="$PATH:/home/rahul/myscripts"' >> ~/.bashrc
source ~/.bashrc
```

---

## 🎨 PS1 — Prompt Customize Karo

```bash
# Default prompt change karo
echo $PS1

# Custom prompt:
export PS1="\u@\h:\w$ "
# \u = username, \h = hostname, \w = current directory

# Colored prompt:
export PS1="\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ "
```

---

## 🏋️ Practice

```bash
# Sab variables dekho
env | sort

# Important ones:
echo "User: $USER"
echo "Home: $HOME"
echo "Shell: $SHELL"
echo "Path: $PATH"

# Custom variable banao
export MY_NAME="Linux Learner"
echo "Hello $MY_NAME"

# .bashrc mein permanently add karo
echo 'export MY_NAME="Linux Learner"' >> ~/.bashrc
source ~/.bashrc
echo $MY_NAME
```

---

## 📝 Aaj Ka Summary

✅ Environment variables = System ki global settings
✅ `env` / `printenv` — sab variables dekho
✅ `export VAR="value"` — variable set karo
✅ `~/.bashrc` — permanent changes yahan likho
✅ `PATH` — commands yahan se dhundhe jaate hain
✅ `source ~/.bashrc` — changes apply karo

---
**Day:** 20/30 | **Topic:** Environment Variables | **Difficulty:** ⭐⭐⭐☆☆
