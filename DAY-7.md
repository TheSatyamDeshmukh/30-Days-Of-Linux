# Day 7 📦 — Package Management

> **"Linux mein software install karna = Mobile pe app download karna!"**

---

## 📱 Package Manager Kya Hota Hai?

Socho **Google Play Store** ya **App Store**:
- Software ka ek bada **store** hai
- Tum naam likhte ho → download + install ho jaata hai
- Updates bhi automatic milti hain
- Delete karna bhi easy

**Linux ka Package Manager bilkul aisa hi hai!** Bas GUI nahi hai — terminal se karte hain.

---

## 🗂️ Kaun Sa Distro, Kaun Sa Manager?

| Linux Distro | Package Manager | Command |
|-------------|----------------|---------|
| Ubuntu / Debian / Mint | **APT** | `apt` |
| CentOS / RHEL / Fedora | **YUM / DNF** | `yum` or `dnf` |
| Arch Linux / Manjaro | **Pacman** | `pacman` |
| openSUSE | **Zypper** | `zypper` |

---

## 🟠 APT — Ubuntu/Debian Ke Liye

### Update (Naye Packages Ki List Laao):
```bash
sudo apt update               # Package list update karo (internet se)
```
> ⚠️ Yeh **system update nahi karta** — sirf available packages ki **list** update karta hai. Install se pehle hamesha `apt update` karo!

### Upgrade (Installed Packages Update Karo):
```bash
sudo apt upgrade              # Sab installed packages update karo
sudo apt full-upgrade         # System upgrade (purane packages hata ke bhi)
```

### Install:
```bash
sudo apt install firefox           # Firefox install karo
sudo apt install vim git curl      # Ek saath kai packages
sudo apt install -y vim            # Confirmation ke bina install (-y = yes)
```

### Remove:
```bash
sudo apt remove firefox            # Firefox remove karo (config files rehti hain)
sudo apt purge firefox             # Firefox + config sab hatao
sudo apt autoremove                # Jo kaam nahi aate woh packages hatao
```

### Search:
```bash
apt search vlc                     # VLC dhundho
apt show firefox                   # Firefox ki info
apt list --installed               # Sab installed packages
apt list --upgradable              # Update karne wale packages
```

### Cache Saaf Karo:
```bash
sudo apt clean                     # Downloaded files hatao
sudo apt autoclean                 # Purani files hatao
```

---

## 🔴 YUM / DNF — CentOS/Fedora Ke Liye

```bash
sudo yum update                    # System update
sudo yum install httpd             # Apache install
sudo yum remove httpd              # Remove
sudo yum search nginx              # Search
sudo yum info nginx                # Info

# DNF (newer version of yum):
sudo dnf update
sudo dnf install nginx
sudo dnf remove nginx
sudo dnf search python
```

---

## ⚫ Pacman — Arch Linux Ke Liye

```bash
sudo pacman -Syu               # System update
sudo pacman -S vim             # Install (S = Sync)
sudo pacman -R vim             # Remove
sudo pacman -Ss firefox        # Search
sudo pacman -Q                 # Installed packages list
sudo pacman -Qs vim            # Installed mein search
```

---

## 📦 .deb / .rpm Files — Manual Install

Kabhi kabhi koi software package manager mein nahi hota — seedha `.deb` ya `.rpm` file download karni padti hai (jaise Windows mein `.exe`).

```bash
# .deb file (Ubuntu/Debian):
sudo dpkg -i package.deb           # Install
sudo dpkg -r packagename           # Remove
dpkg -l                            # Installed list

# .rpm file (CentOS/Fedora):
sudo rpm -ivh package.rpm          # Install
sudo rpm -e packagename            # Remove
rpm -qa                            # Installed list
```

---

## 🔧 Useful Tools Install Karo

```bash
# Aaj yeh install karke try karo:
sudo apt install tree              # Folder tree dikhata hai
sudo apt install htop              # Better process monitor
sudo apt install curl              # URL se data fetch karo
sudo apt install wget              # Files download karo
sudo apt install git               # Version control
sudo apt install net-tools         # ifconfig etc.
sudo apt install unzip             # ZIP files extract karo
```

---

## 🏋️ Practice

```bash
# Step 1: Update karo
sudo apt update

# Step 2: tree install karo
sudo apt install tree

# Step 3: Use karo
tree /home -L 2

# Step 4: Software info dekho
apt show tree

# Step 5: Remove karo
sudo apt remove tree

# Step 6: Confirm karo
tree                   # "command not found" aana chahiye
```

---

## 📝 Aaj Ka Summary

✅ Package Manager = Linux ka App Store
✅ Ubuntu mein `apt`, CentOS mein `yum/dnf`, Arch mein `pacman`
✅ `apt update` → list update | `apt upgrade` → packages update
✅ `apt install` → install | `apt remove` → remove
✅ `.deb` files ke liye `dpkg -i`

---
**Day:** 7/30 | **Topic:** Package Management | **Difficulty:** ⭐⭐☆☆☆
