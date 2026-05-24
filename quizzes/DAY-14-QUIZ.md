# 📝 Day 14 Quiz — Disk & Storage Management

> **Tip:** `df -h` aur `lsblk` chalao — apni disk dekho! 💾

---

## 🟢 Section A — Easy (1 point each)

**Q1.** `df -h` command kya dikhata hai?
- A) Default files B) Disk free space — har partition ka used/free space C) Directory files D) Default home

**Q2.** `/dev/sda` kya represent karta hai?
- A) Software disk A B) Pehli SATA hard disk C) System drive A D) Second disk A

**Q3.** `lsblk` kya karta hai?
- A) List blocked processes B) Block devices (disks, partitions) tree format mein dikhata hai C) Lock blocks D) Linux block check

**Q4.** Partition kya hota hai?
- A) Hard disk ka ek logical section/division B) Computer ka ek part C) File ka division D) Network division

**Q5.** `du -sh ~/Documents` kya dikhata hai?
- A) Documents mein files count B) Documents folder ka total size C) Documents ka path D) Disk usage per file

---

## 🟡 Section B — Medium (2 points each)

**Q6.** `df -h` output mein `Use%` 95% hai. Kya karna chahiye?
- A) Kuch nahi — normal hai B) URGENT — disk almost full! Purani files delete karo ya disk badlo C) Disk format karo D) Reboot karo

**Q7.** `du -sh /* 2>/dev/null | sort -rh | head -5` kya karta hai?
- A) Top 5 files dhundhta hai B) Top 5 largest directories (root level) dikhata hai C) 5 disks check karta hai D) 5 GB files dhundhta hai

**Q8.** `mount` command kisliye use hota hai?
- A) Mountain climbing app B) Storage device ko filesystem mein attach karna C) Monitor mount karna D) Module install karna

**Q9.** `/etc/fstab` file kisliye hoti hai?
- A) File system table — boot pe automatically kaunse partitions mount hon B) Fast boot configuration C) File status backup D) Fstab = firewall settings table

**Q10.** `fdisk -l` kya dikhata hai?
- A) File details B) Sab disks aur unke partitions (size, type) C) Folder details D) Fast disk list

---

## 🔴 Section C — Hard (3 points each)

**Q11.** `mkfs.ext4 /dev/sdb1` kya karta hai?
- A) Disk check karta hai B) /dev/sdb1 pe ext4 filesystem create karta hai C) sdb1 mount karta hai D) sdb1 delete karta hai

**Q12.** `/dev/sda` aur `/dev/sda1` mein kya fark hai?
- A) Koi fark nahi B) `/dev/sda` = poori disk, `/dev/sda1` = us disk ka pehla partition C) sda1 faster hai D) sda1 = system disk

**Q13.** USB drive mount karne ke steps sahi order mein?
- A) Format → Mount → Use B) USB lagao → `lsblk` se naam pata karo → `sudo mount /dev/sdb1 /mnt/usb` → use karo C) USB lagao → automatically mount hoga D) `fdisk` → `mount` → `format`

**Q14.** `inode` kya hota hai Linux mein?
- A) Ek network node B) File ka metadata (permissions, owner, size, location) — actual data nahi C) Input/Output node D) Index node of network

**Q15.** Disk full ho gayi hai `/var/log/` ki wajah se. Kya karoge?
- A) Server restart karo B) `sudo journalctl --vacuum-size=500M` aur `sudo find /var/log -name "*.log" -mtime +7 -delete` C) Poori disk format karo D) New disk lao

---

## 🎯 Bonus (5 points each)

**Q16.** Naya 1TB disk add kiya server pe. Steps kya hain use karne ke liye?
- A) Seedha use karo B) `fdisk` se partition → `mkfs` se format → `mkdir` mount point → `mount` → `/etc/fstab` mein add C) Copy paste karo D) Restart karo

**Q17.** `df -i` command kab useful hota hai?
- A) Koi use nahi B) Jab disk space available hai par nahi files bana pa rahe — inode exhaustion check karna hai C) Interface check D) Important files list

---

## ✅ ANSWERS

<details>
<summary>👆 Answers dekho</summary>

| Q# | Answer | Explanation |
|----|--------|-------------|
| Q1 | B | `df` = disk free. `-h` = human readable |
| Q2 | B | `/dev/sda` = first SATA disk. b=second, c=third. NVMe = `/dev/nvme0n1` |
| Q3 | B | `lsblk` = block devices tree — disks aur partitions |
| Q4 | A | Partition = logical section. Ek physical disk pe multiple partitions |
| Q5 | B | `du -s` = summary, `-h` = human readable |
| Q6 | B | 95% full = serious! Applications crash kar sakte hain |
| Q7 | B | `/` ke direct children ka size, reverse sort, top 5 |
| Q8 | B | Mount = device ko directory se attach karna |
| Q9 | A | `/etc/fstab` = file system table — auto-mount on boot |
| Q10 | B | `fdisk -l` = list partitions. `sudo` chahiye |
| Q11 | B | `mkfs` = make filesystem. `.ext4` = filesystem type |
| Q12 | B | `sda` = whole disk, `sda1`, `sda2` = partitions |
| Q13 | B | Proper mount process: identify → create mountpoint → mount |
| Q14 | B | inode = file metadata store. Each file has one inode |
| Q15 | B | Log cleanup — `journalctl --vacuum` aur find se old logs delete |
| Q16 | B | New disk workflow: partition → format → mount point → mount → fstab |
| Q17 | B | Inode exhaustion — space hai but inodes khatam. `df -i` se check |

</details>

**Total Marks:** 50 | **Day:** 14/30 | **Topic:** Disk & Storage
