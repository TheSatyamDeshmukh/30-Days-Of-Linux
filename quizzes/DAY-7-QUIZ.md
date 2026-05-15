# 📝 Day 7 Quiz — Package Management

> **Tip:** `apt search tree` aur `apt show vim` terminal mein chalao phir quiz do! 📦

---

## 🟢 Section A — Easy (1 point each)

---

**Q1.** Ubuntu mein software install karne ka command kya hai?

- A) `sudo yum install`
- B) `sudo apt install`
- C) `sudo pacman -S`
- D) `sudo install`

---

**Q2.** `apt update` kya karta hai?

- A) Sab installed software update karta hai
- B) Available packages ki list internet se refresh karta hai
- C) System ko update karta hai
- D) APT tool ko update karta hai

---

**Q3.** Software remove karne ka command kya hai Ubuntu mein?

- A) `sudo apt delete`
- B) `sudo apt uninstall`
- C) `sudo apt remove`
- D) `sudo apt clean`

---

**Q4.** `apt search firefox` kya karta hai?

- A) Firefox download karta hai
- B) Firefox install karta hai
- C) Firefox naam se related packages dhundhta hai
- D) Firefox ki location dhundhta hai

---

**Q5.** CentOS/RHEL mein package manager kaun sa hota hai?

- A) apt
- B) pacman
- C) yum / dnf
- D) brew

---

## 🟡 Section B — Medium (2 points each)

---

**Q6.** `apt update` aur `apt upgrade` mein kya fark hai?

- A) Koi fark nahi — dono same hain
- B) `update` = package list refresh karo, `upgrade` = installed packages ko nayi version pe update karo
- C) `update` = system update, `upgrade` = full OS upgrade
- D) `update` faster hai, `upgrade` slow hai

---

**Q7.** `sudo apt install -y vim` mein `-y` flag ka kya matlab hai?

- A) Yesterday's version install karo
- B) Sab confirmation prompts pe automatically "yes" answer do
- C) Yellow mode — warnings dikhao
- D) Yahan install karo (current directory)

---

**Q8.** `apt purge` aur `apt remove` mein kya fark hai?

- A) Koi fark nahi
- B) `purge` = software + uski config files bhi delete, `remove` = sirf software delete (config rehti hai)
- C) `purge` faster hai
- D) `remove` = sirf config delete

---

**Q9.** Sab installed packages list karne ka command kya hai?

- A) `apt list`
- B) `apt list --installed`
- C) `apt show --all`
- D) `dpkg --show`

---

**Q10.** `.deb` file manually install karne ka command kya hai?

- A) `apt install package.deb`
- B) `install package.deb`
- C) `sudo dpkg -i package.deb`
- D) `sudo apt package.deb`

---

## 🔴 Section C — Hard (3 points each)

---

**Q11.** Server pe kaam karte ho. `sudo apt upgrade` karne ke baad system **reboot** maangta hai. Kyun?

- A) Apt ko reboot pasand hai
- B) Kernel ya core system files update hui hain — nayi files load karne ke liye reboot zaroori hai
- C) Disk space free karne ke liye
- D) Users ko logout karne ke liye

---

**Q12.** `sudo apt autoremove` kya karta hai?

- A) Sab packages automatically update karta hai
- B) Jo packages kisi aur package ki dependency the aur ab zaroorat nahi — unhe delete karta hai
- C) Auto-update enable karta hai
- D) Sab packages remove karta hai

---

**Q13.** Package ka poora version, description, dependencies dekhne ka command?

- A) `apt list firefox`
- B) `apt info firefox`
- C) `apt show firefox`
- D) `dpkg -info firefox`

---

**Q14.** Arch Linux mein `pacman -Syu` kya karta hai?

- A) Sirf ek package install karta hai
- B) Package database sync karta hai aur poora system upgrade karta hai
- C) Package search karta hai
- D) Packages uninstall karta hai

---

**Q15.** `sudo apt clean` kyun use karte hain?

- A) Terminal clean karta hai
- B) Downloaded `.deb` package files cache se delete karta hai — disk space free karta hai
- C) Config files delete karta hai
- D) Log files clean karta hai

---

## 🔴 Section D — Distro to Package Manager Match Karo (2 points each)

**Sahi pair choose karo:**

---

**Q16.** Ubuntu 22.04 pe kaam kar rahe ho:

- A) `sudo pacman -S nginx`
- B) `sudo apt install nginx`
- C) `sudo yum install nginx`
- D) `sudo brew install nginx`

---

**Q17.** CentOS 7 pe kaam kar rahe ho:

- A) `sudo apt install python3`
- B) `sudo pacman -S python3`
- C) `sudo yum install python3`
- D) `sudo zypper install python3`

---

**Q18.** Arch Linux pe kaam kar rahe ho:

- A) `sudo apt install git`
- B) `sudo dnf install git`
- C) `sudo pacman -S git`
- D) `sudo rpm -i git`

---

## 🎯 Bonus — Real Scenario (5 points each)

---

**Q19.** Naye Ubuntu server pe pehli baar kaam kar rahe ho. Nginx install karna hai. Sahi order kya hai?

- A) `sudo apt install nginx` → `sudo apt update`
- B) `sudo apt update` → `sudo apt install nginx`
- C) `sudo apt upgrade` → `sudo apt install nginx`
- D) `sudo apt install nginx` directly (update ki zaroorat nahi)

---

**Q20.** `sudo dpkg -i package.deb` chalaya toh yeh error aaya:
```
dpkg: dependency problems prevent configuration of myapp
```
Iska kya matlab hai aur fix kya hai?

- A) File corrupt hai — dobara download karo
- B) Dependencies missing hain — `sudo apt install -f` chalao jo missing dependencies install karega
- C) Root permission nahi — `sudo` add karo
- D) `.deb` file wrong format mein hai

---

---

## ✅ ANSWERS

<details>
<summary>👆 Click karke Answers dekho!</summary>

| Q# | Answer | Explanation |
|----|--------|-------------|
| Q1 | **B** | Ubuntu/Debian = `apt`. `yum` = CentOS, `pacman` = Arch |
| Q2 | **B** | `apt update` sirf **list** refresh karta hai — kuch install/update nahi hota! |
| Q3 | **C** | `apt remove packagename` — config files rehti hain. `apt purge` sab hatata hai |
| Q4 | **C** | `apt search` = package dhundho. Install ke liye `apt install` |
| Q5 | **C** | CentOS/RHEL = `yum` (older) ya `dnf` (newer Fedora/RHEL8+) |
| Q6 | **B** | `update` = list refresh, `upgrade` = actually update karo — dono alag hain! |
| Q7 | **B** | `-y` = `--yes` = sab "Are you sure?" prompts pe auto-yes |
| Q8 | **B** | `purge` = software + config, `remove` = sirf software. Fresh install ke liye `purge` use karo |
| Q9 | **B** | `apt list --installed` — ya `dpkg -l` bhi kaam karta hai |
| Q10 | **C** | `dpkg -i` = Debian package install. `-i` = install |
| Q11 | **B** | Kernel update ke baad nayi kernel load karne ke liye reboot zaroori hai |
| Q12 | **B** | Orphaned packages — jo pehle kisi package ki dependency the, ab kaam ke nahi |
| Q13 | **C** | `apt show packagename` = version, size, dependencies, description sab |
| Q14 | **B** | `-S` = sync/install, `-y` = sysupgrade, `-u` = update. `-Syu` = full system update |
| Q15 | **B** | `/var/cache/apt/archives/` mein downloaded `.deb` files hoti hain — `clean` se disk free |
| Q16 | **B** | Ubuntu = apt |
| Q17 | **C** | CentOS 7 = yum |
| Q18 | **C** | Arch Linux = pacman |
| Q19 | **B** | Hamesha pehle `update` (list refresh) phir `install` — warna purani list se install hoga! |
| Q20 | **B** | Dependency error = `apt install -f` (`-f` = fix broken) automatically missing packages install karta hai |

</details>

---

## 📊 Score Calculator

| Score | Result |
|-------|--------|
| 50-60 | 🏆 **Package Pro!** |
| 37-49 | 🥈 **Good!** |
| 24-36 | 🥉 **Practice karo** |
| 0-23  | 📖 **DAY-7.md dobara padho** |

**Total Marks:** 60

---

## 💻 Practical Challenge

```bash
# 1. Package list update karo
sudo apt update

# 2. tree install karo
sudo apt install tree -y

# 3. Use karo
tree /home -L 2

# 4. Package info dekho
apt show tree

# 5. Update karne laayak packages dekho
apt list --upgradable 2>/dev/null | head -10

# 6. Remove karo
sudo apt remove tree -y

# 7. Confirm karo
tree          # "command not found" aana chahiye!

# 8. Cache clean karo
sudo apt clean
sudo apt autoremove -y
```

---
**Quiz:** Day 7/30 | **Total Marks:** 60 | **Topic:** Package Management
