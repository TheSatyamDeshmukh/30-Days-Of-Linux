# Day 4 🔐 — File Permissions

> **"Linux mein har file ka ek 'darwaan' hota hai — permissions!"**

---

## 🤔 Permissions Kyun Zaroori Hain?

Socho tumhare school mein:
- **Principal** = sab kuch kar sakta hai
- **Teacher** = sirf apni class dekh sakta hai
- **Student** = sirf apna kaam kar sakta hai

Linux mein bhi aisa hi hota hai! Har file ke liye decide hota hai — **kaun padh sakta hai, kaun likh sakta hai, kaun chala sakta hai.**

---

## 👁️ Permissions Kaise Dekhen?

```bash
ls -l
```

**Output:**
```
-rwxr-xr-- 1 rahul developers 1234 Jan 15 notes.txt
```

**Iska Matlab:**
```
- rwx r-x r--
↑  ↑   ↑   ↑
│  │   │   └── Others (baaki sab log) — r-- = sirf padh sakte
│  │   └────── Group (developers group) — r-x = padh + chala sakte
│  └────────── Owner (rahul) — rwx = sab kuch kar sakta
└───────────── File type (- = file, d = directory)
```

---

## 🔤 r, w, x Ka Matlab

| Letter | Naam | File Pe Matlab | Folder Pe Matlab |
|--------|------|----------------|-----------------|
| `r` | Read | File **padh** sako | Folder ki **list** dekh sako |
| `w` | Write | File mein **likh** sako | Folder mein **files bana/mita** sako |
| `x` | Execute | File **chala** sako (script/program) | Folder mein **ja** sako (`cd`) |
| `-` | None | Koi permission nahi | Koi permission nahi |

---

## 🔢 Numbers Wala System (Octal)

Har permission ko number se bhi represent karte hain:

| Permission | Number |
|-----------|--------|
| `r` (read) | **4** |
| `w` (write) | **2** |
| `x` (execute) | **1** |
| `-` (none) | **0** |

**Jodne ka tarika:**
```
rwx = 4+2+1 = 7
rw- = 4+2+0 = 6
r-x = 4+0+1 = 5
r-- = 4+0+0 = 4
--- = 0+0+0 = 0
```

**Common Combinations:**
```
755 = rwxr-xr-x   (scripts ke liye)
644 = rw-r--r--   (normal files ke liye)
600 = rw-------   (private files ke liye)
777 = rwxrwxrwx   (sab kuch, sabko — AVOID karo!)
```

---

## ⚙️ `chmod` — Permissions Badlo

**Full Name:** Change Mode

```bash
# Number se
chmod 755 script.sh         # Owner: rwx, Group: r-x, Others: r-x
chmod 644 notes.txt         # Owner: rw-, Group: r--, Others: r--
chmod 600 secret.txt        # Sirf owner padh/likh sakta

# Letter se (zyada easy!)
chmod +x script.sh          # Sabko execute permission do
chmod -x script.sh          # Execute permission hatao
chmod u+x script.sh         # Sirf owner (u=user) ko execute do
chmod g+w file.txt          # Group ko write permission do
chmod o-r file.txt          # Others se read permission hatao
chmod a+r file.txt          # Sabko (a=all) read do
```

**u, g, o, a Ka Matlab:**
```
u = user (owner)
g = group
o = others
a = all (sab)
```

---

## 👤 `chown` — Owner Badlo

**Full Name:** Change Owner

```bash
sudo chown rahul file.txt           # Owner badlo
sudo chown rahul:developers file.txt # Owner aur group dono badlo
sudo chown -R rahul myfolder/       # Folder aur andar sab ka owner badlo
```

> ⚠️ `chown` ke liye `sudo` chahiye!

---

## 👥 `chgrp` — Group Badlo

```bash
sudo chgrp developers file.txt      # Group badlo
sudo chgrp -R developers folder/    # Folder ka group badlo
```

---

## 🔍 Real Examples

```bash
# Script banao aur chalao
touch myscript.sh
echo '#!/bin/bash' > myscript.sh
echo 'echo "Hello!"' >> myscript.sh
chmod +x myscript.sh
./myscript.sh                       # Chalega ab!

# Private file banao
touch secret.txt
echo "Mera password" > secret.txt
chmod 600 secret.txt                # Sirf tum padh sako
ls -l secret.txt                    # -rw------- dikhega

# Folder ko restrict karo
mkdir private_folder
chmod 700 private_folder            # Sirf owner ja sakta
```

---

## 🏋️ Practice

```bash
# Ek file banao
touch test.txt

# Permissions dekho
ls -l test.txt

# Execute permission do
chmod +x test.txt
ls -l test.txt                      # x ab dikhega

# Private banao
chmod 600 test.txt
ls -l test.txt                      # -rw------- dikhega

# Normal wapas karo
chmod 644 test.txt
ls -l test.txt                      # -rw-r--r-- dikhega
```

---

## 📝 Aaj Ka Summary

✅ `r`=Read, `w`=Write, `x`=Execute
✅ Teen groups: **Owner**, **Group**, **Others**
✅ Numbers: `r=4`, `w=2`, `x=1`
✅ `chmod` — permissions badlo
✅ `chown` — owner badlo
✅ `755` scripts ke liye, `644` normal files ke liye

---
**Day:** 4/30 | **Topic:** File Permissions | **Difficulty:** ⭐⭐⭐☆☆
