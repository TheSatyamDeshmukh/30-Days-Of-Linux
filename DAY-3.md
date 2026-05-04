# Day 3 📁 — Linux File System

> **"Linux mein sab kuch ek file hai — even hardware bhi!"**

---

## 🌳 Linux Ka File System — Ek Bada Ped!

Linux ka file system ek **ulte ped** jaisa hai. Sabse upar **root** (`/`) hota hai — jaise ped ki jad. Ussi se saari branches nikalti hain.

```
/ (Root — Sabse Upar)
├── 🏠 home/          ← Users ke personal folders
│   └── rahul/        ← Tumhara ghar!
├── ⚙️ etc/           ← System settings/config files
├── 📦 usr/           ← Programs aur libraries
├── 🔧 bin/           ← Basic commands (ls, cd, etc.)
├── 🚀 sbin/          ← Admin commands (root ke liye)
├── 💾 var/           ← Variable data (logs, databases)
│   └── log/          ← System logs
├── 🗑️ tmp/           ← Temporary files (restart pe saaf!)
├── 🔌 dev/           ← Hardware devices (hard disk, USB)
├── 📊 proc/          ← Running processes ki info (virtual!)
├── 🏔️ mnt/           ← Mounted drives (USB, external)
├── 📱 media/         ← Auto-mounted devices
├── 💿 boot/          ← Boot files (GRUB, kernel)
├── 📚 lib/           ← System libraries
└── 🌐 srv/           ← Server data
```

---

## 📂 Har Folder Ka Kaam

### 🏠 `/home` — Tumhara Ghar

```bash
ls /home                  # Sab users ke folders dikhte hain
ls /home/rahul            # Tumhara personal folder
echo $HOME                # Tumhara home path
cd ~                      # Home mein jao (shortcut)
```

Tumhare **Documents, Downloads, Desktop, Music** sab yahan hain. Sirf tumhara access hota hai yahan (usually).

---

### ⚙️ `/etc` — System Ki Settings

```bash
ls /etc                   # Kai config files hain
cat /etc/hostname         # Computer ka naam
cat /etc/os-release       # Kaun sa Linux hai?
cat /etc/passwd           # Users ki list (password nahi, sirf list!)
cat /etc/hosts            # IP address → name mapping
```

**`/etc` = "Everything To Configure"** (khud se banaya hua yaad karne ka tarika 😄)

Config files yahan text format mein hote hain — normal text editor se dekh sakte ho!

---

### 💾 `/var` — Badalne Wali Cheezein

```bash
ls /var
ls /var/log               # Log files yahan hain
tail -f /var/log/syslog   # System log live dekho
du -sh /var/log/          # Log files kitni jagah le rahi hain
```

Logs, databases, mail sab `/var` mein hote hain — yeh directory size mein badhti rehti hai.

---

### 🗑️ `/tmp` — Temporary Files

```bash
ls /tmp
touch /tmp/test.txt       # Yahan file banao
# Computer restart karo — file GONE! 💨
```

Programs yahan apni temporary files rakhte hain. Restart pe saaf ho jaata hai automatically.

---

### 🔌 `/dev` — Hardware Devices

```bash
ls /dev
ls /dev/sd*               # Hard disks aur partitions
ls /dev/tty*              # Terminals
cat /dev/null             # Kuch nahi! (Black hole of Linux)
```

Linux mein **sab kuch ek file hai** — hard disk bhi (`/dev/sda`), keyboard bhi, screen bhi! Yeh Linux ki philosophy hai.

---

### 📊 `/proc` — Chal Rahe Programs Ki Info

```bash
ls /proc                  # Numbers = Process IDs
cat /proc/cpuinfo         # CPU ki information
cat /proc/meminfo         # RAM ki information
cat /proc/version         # Linux version
```

`/proc` ek **virtual filesystem** hai — disk pe nahi hai actually! Kernel live information yahan expose karta hai.

---

### 📦 `/usr` — Programs Yahan Hain

```bash
ls /usr/bin               # Installed programs (firefox, python, etc.)
ls /usr/lib               # Libraries
ls /usr/share             # Shared data, documentation
which python3             # Python kahan install hai?
```

---

### 🔧 `/bin` aur `/sbin`

```bash
ls /bin                   # Basic commands: ls, cp, mv, cat (yahan hain!)
ls /sbin                  # Admin commands: fdisk, iptables
```

---

## 🔍 Path Samajhna — Full Example

```bash
/home/rahul/Documents/linux/notes.txt
 ↑     ↑       ↑        ↑       ↑
Root  User   Folder   Folder   File
```

---

## 📝 Useful Commands

```bash
tree                      # Folder tree dikhao (install: sudo apt install tree)
tree -L 2                 # 2 levels tak dikhao
file notes.txt            # Yeh file ka type kya hai?
stat notes.txt            # File ki full information
du -sh ~/Documents        # Documents folder ka size
df -h                     # Disk space kitna bacha hai
```

---

## 🏋️ Practice

```bash
ls /                       # Root dekho
ls /etc | head -20         # Pehle 20 config files dekho
cat /etc/os-release        # Kaun sa Linux hai?
cat /proc/cpuinfo | grep "model name"   # CPU kaun sa hai?
cat /proc/meminfo | grep MemTotal       # Total RAM?
df -h                      # Disk space check
```

---

**Day:** 3/30 | **Topic:** Linux File System | **Difficulty:** ⭐⭐☆☆☆
