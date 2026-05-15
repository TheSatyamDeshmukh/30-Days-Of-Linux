# Day 14 💾 — Disk & Storage Management

> **"Disk bharne se pehle manage karna seekho!"**

---

## 📊 Disk Space Dekhna

```bash
df -h                     # Disk space (human readable — GB, MB mein)
df -h /                   # Sirf root partition
df -i                     # Inode usage
du -sh ~/Documents        # Documents folder ka size
du -sh *                  # Current folder mein sab ka size
du -sh * | sort -h        # Size se sort karo
du -sh */ 2>/dev/null | sort -rh | head -10  # Top 10 bade folders
```

---

## 💿 Disks aur Partitions Dekhna

```bash
lsblk                     # Block devices (disks, partitions) tree mein
lsblk -f                  # Filesystem info ke saath
fdisk -l                  # Sab disks aur partitions (sudo chahiye)
sudo fdisk -l /dev/sda    # Specific disk
blkid                     # UUID aur filesystem type
```

**Device Names Samajhna:**
```
/dev/sda    ← Pehli hard disk
/dev/sda1   ← Pehli disk ka pehla partition
/dev/sda2   ← Pehli disk ka doosra partition
/dev/sdb    ← Doosri hard disk (USB, etc.)
/dev/nvme0n1 ← NVMe SSD
```

---

## 🔗 Mount Karna

Mount matlab — disk ya partition ko Linux file system mein **attach karna**.

```bash
mount                     # Abhi kya kya mounted hai?
sudo mount /dev/sdb1 /mnt/usb      # USB mount karo
sudo umount /mnt/usb               # Unmount karo
sudo mount -t ext4 /dev/sdb1 /mnt  # Filesystem type specify karo
```

**Auto-mount (/etc/fstab):**
```bash
cat /etc/fstab            # Auto-mount config
# Format: DEVICE  MOUNTPOINT  FSTYPE  OPTIONS  DUMP  PASS
# UUID=xxx  /  ext4  errors=remount-ro  0  1
```

---

## 🆕 Partition Banana (fdisk)

```bash
sudo fdisk /dev/sdb       # Disk par kaam karo
# Commands inside fdisk:
# m = help
# n = new partition
# d = delete partition
# p = print partitions
# w = write (save) karo
# q = quit bina save ke
```

---

## 📝 Filesystem Banana

```bash
sudo mkfs.ext4 /dev/sdb1           # ext4 filesystem banao
sudo mkfs.xfs /dev/sdb1            # XFS filesystem
sudo mkfs.fat -F32 /dev/sdb1       # FAT32 (USB ke liye)
sudo mkfs.ntfs /dev/sdb1           # NTFS (Windows ke liye)
```

---

## 🔍 Disk Health Check

```bash
sudo fsck /dev/sda1               # Filesystem check (unmounted hona chahiye)
sudo badblocks -v /dev/sda        # Bad blocks dhundho
sudo smartctl -a /dev/sda         # SMART data (sudo apt install smartmontools)
```

---

## 🏋️ Practice

```bash
df -h
lsblk
du -sh ~/*  2>/dev/null | sort -rh | head -5
mount | grep -v tmpfs | grep -v cgroup
```

-e 
**Day:** 14/30 | **Topic:** Disk & Storage | **Difficulty:** ⭐⭐⭐☆☆
