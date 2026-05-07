# Day 6 👤 — Users & Groups

> **"Linux ek shared ghar hai — har user ka apna kamra hota hai!"**

---

## 🏠 Users Ka Concept

Socho ek **hostel** hai jahan kai students rehte hain:
- Har student ka **apna kamra** hai (home folder)
- **Warden** (root user) ke paas **master key** hai — sab jagah ja sakta hai
- Students apne doosre ke kamre mein nahi ja sakte (by default)

Linux mein bilkul aisa hi system hai!

---

## 👑 Root User — Sabka Boss

```bash
whoami                    # Main kaun hoon?
id                        # Meri user ID aur groups
sudo whoami               # root ki tarah kaun hoon?
```

**Root user** ke paas **unlimited powers** hain — koi bhi file delete kar sakta hai, koi bhi command chala sakta hai. Isliye **root se carefully kaam karo!**

---

## 🔍 Users Dekhna

```bash
cat /etc/passwd           # Sab users ki list
cut -d: -f1 /etc/passwd   # Sirf usernames
whoami                    # Current user
id                        # Current user ka ID
id username               # Kisi bhi user ka ID
w                         # Abhi kaun logged in hai?
who                       # Logged in users
last                      # Login history
```

**`/etc/passwd` Format:**
```
rahul:x:1000:1000:Rahul Kumar:/home/rahul:/bin/bash
  ↑   ↑   ↑     ↑       ↑          ↑           ↑
User Pass UID  GID    Name      Home        Shell
```

---

## ➕ Naya User Banana

```bash
sudo useradd priya                    # Basic user banana
sudo useradd -m priya                 # Home folder ke saath
sudo useradd -m -s /bin/bash priya    # Bash shell ke saath
sudo useradd -m -G sudo priya         # Sudo group mein bhi add karo
sudo passwd priya                     # Password set karo
```

---

## ❌ User Delete Karna

```bash
sudo userdel priya                    # User delete (home folder rehta hai)
sudo userdel -r priya                 # User + home folder dono delete
```

---

## ✏️ User Modify Karna

```bash
sudo usermod -s /bin/bash rahul       # Shell badlo
sudo usermod -d /home/newpath rahul   # Home folder badlo
sudo usermod -aG sudo rahul           # Sudo group mein ADD karo
sudo usermod -aG docker rahul         # Docker group mein add karo
sudo usermod -l newname oldname       # Username badlo
sudo usermod -L rahul                 # Account lock karo
sudo usermod -U rahul                 # Account unlock karo
```

> ⚠️ `-aG` mein `-a` (append) zaroori hai! Bina `-a` ke purane groups chale jaate hain!

---

## 👥 Groups

Groups matlab — **ek team**. Ek group ke saare members ek saath kisi file ko access kar sakte hain.

```bash
cat /etc/group            # Sab groups ki list
groups                    # Main kis kis group mein hoon?
groups rahul              # Rahul kis kis group mein hai?
```

**Naya Group Banana:**
```bash
sudo groupadd developers          # Group banao
sudo groupadd -g 1500 designers   # Specific GID ke saath
```

**Group Mein User Add Karo:**
```bash
sudo gpasswd -a rahul developers  # rahul ko developers mein add karo
sudo usermod -aG developers rahul # Doosra tarika
```

**Group Se User Hatao:**
```bash
sudo gpasswd -d rahul developers  # rahul ko developers se hatao
```

**Group Delete Karo:**
```bash
sudo groupdel developers
```

---

## 🔑 sudo — Admin Powers

`sudo` matlab — "Super User DO" — ek command ko admin (root) ki tarah chalao.

```bash
sudo apt update                   # Admin ki tarah update karo
sudo rm /etc/important.conf       # Admin ki tarah delete karo
sudo -i                           # Root shell mein jao (careful!)
sudo -u priya command             # Priya ke roop mein command chalao
sudo !!                           # Pichli command sudo ke saath dobara chalao
```

**Sudo Access Dena:**
```bash
sudo usermod -aG sudo rahul       # Ubuntu mein
sudo usermod -aG wheel rahul      # CentOS/Fedora mein
```

---

## 🔐 Password Management

```bash
passwd                            # Apna password badlo
sudo passwd priya                 # Priya ka password badlo
sudo passwd -l priya              # Account lock (login band)
sudo passwd -u priya              # Account unlock
sudo passwd -e priya              # Password expire karo (next login pe change karna hoga)
sudo chage -l rahul               # Password expiry info dekho
```

---

## 🔄 User Switch Karna

```bash
su priya                          # Priya ke roop mein login karo
su - priya                        # Priya ke environment ke saath login
su -                              # Root mein jao (password chahiye)
exit                              # Wapas apne user mein
```

---

## 🏋️ Practice

```bash
# Apni info dekho
whoami
id
groups

# Naya user banao
sudo useradd -m testuser
sudo passwd testuser
# (koi bhi password set karo)

# User switch karo
su - testuser
whoami                            # testuser dikhega
exit                              # Wapas

# User delete karo
sudo userdel -r testuser
cat /etc/passwd | grep testuser   # Gone!
```

---

## 📝 Aaj Ka Summary

✅ `whoami` / `id` — apni info
✅ `useradd` — naya user banana
✅ `passwd` — password set karna
✅ `usermod -aG` — group mein add karna
✅ `sudo` — admin powers
✅ `su` — user switch karna
✅ Root user — sabka boss, carefully use karo!

---
**Day:** 6/30 | **Topic:** Users & Groups | **Difficulty:** ⭐⭐⭐☆☆
