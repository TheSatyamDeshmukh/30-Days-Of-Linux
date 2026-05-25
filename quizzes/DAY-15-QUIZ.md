# 📝 Day 15 Quiz — Archiving & Compression

> **Tip:** `tar -czvf test.tar.gz /tmp/` try karo! 🗜️

---

## 🟢 Section A — Easy (1 point each)

**Q1.** `tar` ka full form kya hai?
- A) Transfer Archive Resource B) Tape Archive C) Text Archive D) Terminal Archive

**Q2.** `tar -czvf backup.tar.gz folder/` mein `c` flag ka matlab?
- A) Copy B) Create archive C) Compress D) Check

**Q3.** `.tar.gz` file extract karne ka command?
- A) `tar -czvf file.tar.gz` B) `tar -xzvf file.tar.gz` C) `untar file.tar.gz` D) `extract file.tar.gz`

**Q4.** `gzip file.txt` ke baad original file ka kya hota hai?
- A) Remain rehti hai B) Delete ho jaati hai — sirf `file.txt.gz` banti hai C) Rename hoti hai D) Backup mein jaati hai

**Q5.** Windows ZIP files Linux mein extract karne ka command?
- A) `tar -x file.zip` B) `unzip file.zip` C) `extract file.zip` D) `gzip -d file.zip`

---

## 🟡 Section B — Medium (2 points each)

**Q6.** `tar -czvf` mein `z` flag ka matlab?
- A) Zero compression B) gzip compression use karo C) zip format D) Zone specific

**Q7.** Archive ki contents dekhna bina extract kiye?
- A) `tar -xvf archive.tar` B) `tar -tvf archive.tar` C) `cat archive.tar` D) `ls archive.tar`

**Q8.** `gzip -k file.txt` mein `-k` ka matlab?
- A) Kill compression B) Keep original file bhi C) Key based compression D) KB size mein

**Q9.** Sabse best compression ratio kaun deta hai (slow but smallest)?
- A) gzip (.gz) B) bzip2 (.bz2) C) xz (.xz) D) zip (.zip)

**Q10.** `tar -xzvf backup.tar.gz -C /restore/` mein `-C /restore/` ka matlab?
- A) Create /restore/ folder B) Current folder /restore/ pe extract karo C) Check /restore/ D) Copy to /restore/

---

## 🔴 Section C — Hard (3 points each)

**Q11.** Daily backup script mein date-based filename banana hai. Sahi command?
- A) `tar -czvf backup.tar.gz folder/` B) `tar -czvf "backup_$(date +%Y-%m-%d).tar.gz" folder/` C) `tar -czvf backup_DATE.tar.gz folder/` D) `tar -czvf backup.tar.gz folder/ --date`

**Q12.** `tar -cjvf archive.tar.bz2 folder/` mein `j` flag ka matlab?
- A) Join files B) bzip2 compression C) Just compress D) Java mode

**Q13.** 10GB folder compress karna hai — speed important hai, size zyada matter nahi. Kaun sa format?
- A) xz (.xz) — best compression but slowest B) gzip (.gz) — good balance, fast C) bzip2 (.bz2) D) zip (.zip)

**Q14.** Sirf ek specific file extract karni hai `archive.tar.gz` se:
- A) `tar -xzvf archive.tar.gz` B) `tar -xzvf archive.tar.gz path/to/file.txt` C) `tar -extract file.txt archive.tar.gz` D) `unzip archive.tar.gz file.txt`

**Q15.** Compressed file ka size original se compare karne ke liye?
- A) `compare file.txt file.txt.gz` B) `ls -lh file.txt file.txt.gz` C) `size file.txt` D) `gzip --size file.txt`

---

## 🎯 Bonus (5 points each)

**Q16.** `/home/rahul` ka daily backup `/backup/` mein date-wise banana hai aur 7 din purane delete karne hain. Script snippet kya hoga?
```bash
DATE=$(date +%Y-%m-%d)
tar -czvf /backup/home_$DATE.tar.gz /home/rahul/
find /backup/ -name "home_*.tar.gz" ___ -delete
```
`___` mein kya aayega?
- A) `-old 7` B) `-mtime +7` C) `-days 7` D) `-age +7`

**Q17.** `.tar.gz` vs `.zip` — production server pe kaunsa better aur kyun?
- A) .zip always better B) `.tar.gz` better — permissions/ownership preserve karta hai, `.zip` Linux permissions lose karta hai C) Koi fark nahi D) .zip smaller hota hai

---

## ✅ ANSWERS

<details>
<summary>👆 Answers dekho</summary>

| Q# | Answer | Explanation |
|----|--------|-------------|
| Q1 | B | tar = Tape Archive — originally magnetic tapes ke liye |
| Q2 | B | `-c` = create. `-x`=extract, `-t`=list, `-r`=append |
| Q3 | B | `-x`=extract, `-z`=gzip, `-v`=verbose, `-f`=file |
| Q4 | B | `gzip` original file replace karta hai compressed se. `-k` se dono rakhte hain |
| Q5 | B | `unzip` = ZIP format. `sudo apt install unzip` |
| Q6 | B | `-z` = gzip filter. `-j` = bzip2, `-J` = xz |
| Q7 | B | `-t` = list (table of contents). Bina extract kiye dekho |
| Q8 | B | `-k` = keep original. Default mein gzip original delete karta hai |
| Q9 | C | xz = best compression ratio but slowest. Good for distribution |
| Q10 | B | `-C directory` = change to directory before extracting |
| Q11 | B | `$(date +%Y-%m-%d)` = dynamic date in filename |
| Q12 | B | `-j` = bzip2 compression (.tar.bz2) |
| Q13 | B | Speed priority = gzip. Size priority = xz |
| Q14 | B | Specific file extract: `tar -xzvf archive.tar.gz path/inside/archive` |
| Q15 | B | `ls -lh` = human readable sizes side by side |
| Q16 | B | `find -mtime +7` = older than 7 days |
| Q17 | B | tar preserves Unix permissions, ownership, symlinks — zip nahi karta |

</details>

**Total Marks:** 50 | **Day:** 15/30 | **Topic:** Archiving & Compression
