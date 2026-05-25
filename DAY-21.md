# Day 21 🗂️ — Linux Filesystem Hierarchy Standard (FHS)

> **"Linux mein har cheez ki ek jagah hai — aur woh jagah kyun hai, aaj samjhenge!"**

---

## 🌳 Complete FHS Map

```
/ (Root — Sab ka baap!)
│
├── /bin     → Basic commands (ls, cp, mv — sab users ke liye)
├── /sbin    → System commands (fdisk, iptables — admin ke liye)
├── /usr     → User programs
│   ├── /usr/bin    → Additional commands
│   ├── /usr/sbin   → Additional system commands
│   ├── /usr/lib    → Libraries
│   ├── /usr/share  → Shared data, man pages
│   └── /usr/local  → Tumhare khud ke install kiye programs
├── /home    → Users ke ghar
│   └── /home/rahul → Tumhara personal space
├── /root    → Root user ka ghar
├── /etc     → Configuration files
│   ├── /etc/apt        → APT config
│   ├── /etc/ssh        → SSH config
│   ├── /etc/nginx      → Nginx config
│   └── /etc/systemd    → Systemd configs
├── /var     → Variable data (badlta rehta hai)
│   ├── /var/log        → System logs
│   ├── /var/www        → Web files
│   ├── /var/lib        → App data (databases etc.)
│   └── /var/tmp        → Temp files (reboot ke baad bhi rehta)
├── /tmp     → Temporary (reboot pe saaf!)
├── /dev     → Device files
│   ├── /dev/sda        → First hard disk
│   ├── /dev/null       → Black hole!
│   ├── /dev/zero       → Zeros generate karta hai
│   └── /dev/random     → Random numbers
├── /proc    → Kernel ki live info (virtual)
│   ├── /proc/cpuinfo   → CPU info
│   ├── /proc/meminfo   → RAM info
│   └── /proc/[PID]/    → Process info
├── /sys     → Kernel aur hardware info (virtual)
├── /mnt     → Manual mount point
├── /media   → Auto-mount (USB, CD)
├── /boot    → Boot files
│   ├── vmlinuz         → Linux kernel
│   └── grub/           → GRUB bootloader
├── /lib     → System libraries
├── /lib64   → 64-bit libraries
├── /opt     → Optional software (third-party apps)
├── /srv     → Service data (web server files)
└── /run     → Runtime data (reboot pe saaf)
```

---

## 🔍 Important Paths Explore Karo

```bash
# /proc — Live system info
cat /proc/cpuinfo                  # CPU details
cat /proc/meminfo                  # Memory details
cat /proc/version                  # Linux version
cat /proc/uptime                   # Uptime in seconds
ls /proc/ | head -20               # Running processes!

# /dev — Devices
ls /dev/sd*                        # Hard disks
ls /dev/tty*                       # Terminals
echo "test" > /dev/null            # Discard output (black hole!)
dd if=/dev/zero bs=1M count=10 of=test.img  # 10MB zero file banao

# /etc — Config files
ls /etc/ | sort
cat /etc/hostname                  # Computer naam
cat /etc/timezone                  # Timezone
cat /etc/shells                    # Available shells

# /var/log — Logs
ls /var/log/
tail -5 /var/log/syslog
```

---

## 🏋️ Practice

```bash
# Explorer ban jao!
ls /
cat /proc/cpuinfo | grep "model name" | head -1
cat /proc/meminfo | grep MemTotal
ls /dev/sd* 2>/dev/null || echo "No SATA disks"
ls /etc | wc -l                    # Kitni config files hain?
du -sh /var/log/                   # Logs kitni jagah le rahe?
```

---

**Day:** 21/30 | **Topic:** Filesystem Hierarchy | **Difficulty:** ⭐⭐☆☆☆
