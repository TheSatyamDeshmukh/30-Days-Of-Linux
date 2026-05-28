# Day 23 🧬 — Kernel & Boot Process

> **"Computer ON karne se login screen tak — yeh 30 second ka safar!"**

---

## 🚀 Boot Process — Step by Step

```
Power Button Press
        ↓
   1. BIOS/UEFI
        ↓
   2. POST (Power-On Self Test)
        ↓
   3. Boot Device Select karo
        ↓
   4. GRUB (Bootloader)
        ↓
   5. Linux Kernel Load
        ↓
   6. initramfs
        ↓
   7. Systemd (PID 1)
        ↓
   8. Services Start
        ↓
   9. Login Screen / Shell
```

---

## 1️⃣ BIOS/UEFI

**BIOS** = Basic Input/Output System (purana, 1970s se)
**UEFI** = Unified Extensible Firmware Interface (nayi, faster)

Yeh hardware check karta hai aur bootloader dhundhta hai.

---

## 2️⃣ GRUB — Bootloader

GRUB = GRand Unified Bootloader

```bash
# GRUB config
cat /etc/default/grub             # Main config
ls /boot/grub/                    # GRUB files

# GRUB update karo (config change ke baad)
sudo update-grub                  # Ubuntu/Debian
sudo grub2-mkconfig -o /boot/grub2/grub.cfg  # CentOS

# Boot timeout change karo:
sudo nano /etc/default/grub
# GRUB_TIMEOUT=5  ← 5 seconds wait
sudo update-grub
```

---

## 3️⃣ Linux Kernel

```bash
uname -r                          # Current kernel version
uname -a                          # Poori info
ls /boot/                         # Kernel files yahan hain
# vmlinuz-5.15.0-91-generic ← Compressed kernel

# Installed kernels dekho
dpkg --list | grep linux-image

# Kernel modules
lsmod                             # Loaded modules
modinfo usb_storage               # Module info
sudo modprobe module_name         # Module load karo
sudo modprobe -r module_name      # Module unload karo
```

---

## 4️⃣ initramfs

Temporary filesystem jo kernel ke saath load hota hai — asli filesystem mount karne mein help karta hai.

```bash
ls /boot/initrd*                  # initramfs files
```

---

## 5️⃣ Systemd — PID 1

```bash
# Systemd check
ps -p 1                           # PID 1 = systemd!
systemctl status                  # Overall system status
systemd-analyze                   # Boot time
systemd-analyze blame             # Kaun zyada time le raha?
```

---

## 🔧 Kernel Parameters

```bash
# Current parameters dekho
cat /proc/cmdline

# Runtime parameters
sysctl -a                         # Sab parameters
sysctl net.ipv4.ip_forward        # Specific parameter
sudo sysctl -w net.ipv4.ip_forward=1  # Change karo (temporary)

# Permanent:
sudo nano /etc/sysctl.conf
# net.ipv4.ip_forward = 1
sudo sysctl -p                    # Apply karo
```

---

## 🏋️ Practice

```bash
uname -r
uname -a
cat /proc/cmdline
systemd-analyze
systemd-analyze blame | head -10
ls /boot/
lsmod | wc -l                     # Kitne modules loaded hain?
```

---

**Day:** 23/30 | **Topic:** Kernel & Boot Process | **Difficulty:** ⭐⭐⭐⭐☆
