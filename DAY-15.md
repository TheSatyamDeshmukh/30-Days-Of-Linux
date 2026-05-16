# Day 15 🗜️ — Archiving & Compression

> **"Files ko pack karo — share karna aur backup lena easy ho jaayega!"**

---

## 📦 tar — Archive Banana

`tar` = Tape Archive. Files ko ek file mein band karta hai.

```bash
# Archive BANANA:
tar -cvf archive.tar folder/          # Create verbose archive
tar -czvf archive.tar.gz folder/      # Create + gzip compress
tar -cjvf archive.tar.bz2 folder/     # Create + bzip2 compress

# Archive KHOLNA:
tar -xvf archive.tar                  # Extract
tar -xzvf archive.tar.gz              # Extract gzip
tar -xjvf archive.tar.bz2            # Extract bzip2
tar -xvf archive.tar -C /path/        # Specific folder mein extract

# DEKHNA (extract kiye bina):
tar -tvf archive.tar                  # List contents
tar -tzvf archive.tar.gz

# Flags Yaad Karne Ka Tarika:
# c = Create
# x = eXtract
# v = Verbose (kya ho raha hai dikhao)
# f = File naam aata hai
# z = gZip
# j = bzip2
```

---

## 📦 gzip / gunzip

```bash
gzip file.txt                 # file.txt → file.txt.gz (original delete hota hai!)
gzip -k file.txt              # Keep original bhi (-k)
gzip -9 file.txt              # Maximum compression
gunzip file.txt.gz            # Uncompress
gzip -d file.txt.gz           # Same as gunzip
zcat file.txt.gz              # Bina extract kiye dekho
```

---

## 📦 zip / unzip

```bash
zip archive.zip file1 file2        # Files zip karo
zip -r archive.zip folder/         # Folder zip karo
zip -r -9 archive.zip folder/      # Maximum compression
unzip archive.zip                  # Extract karo
unzip archive.zip -d /path/        # Specific folder mein extract
unzip -l archive.zip               # List dekho (extract kiye bina)
unzip -v archive.zip               # Verbose list
```

---

## 📦 bzip2 / xz

```bash
bzip2 file.txt                # .bz2 banao
bunzip2 file.txt.bz2          # Extract karo

xz file.txt                   # .xz banao (best compression!)
xz -d file.txt.xz             # Extract karo
xz -k file.txt                # Original rakhte hue
```

---

## 🔢 Compression Comparison

| Format | Extension | Speed | Size |
|--------|-----------|-------|------|
| gzip | .gz | ⚡⚡⚡ Fast | Medium |
| bzip2 | .bz2 | ⚡⚡ Medium | Good |
| xz | .xz | ⚡ Slow | Best |
| zip | .zip | ⚡⚡⚡ Fast | Medium |

**Recommendation:** Daily use ke liye `.tar.gz`, maximum compression ke liye `.tar.xz`

---

## 🏋️ Practice

```bash
# Folder banao aur files daalo
mkdir test_archive
echo "File 1" > test_archive/file1.txt
echo "File 2" > test_archive/file2.txt
echo "File 3" > test_archive/file3.txt

# Archive banao
tar -czvf backup.tar.gz test_archive/

# Size compare karo
ls -lh test_archive/
ls -lh backup.tar.gz

# Extract karo
mkdir extracted
tar -xzvf backup.tar.gz -C extracted/
ls extracted/

# Saaf karo
rm -rf test_archive extracted backup.tar.gz
```

-e 
**Day:** 15/30 | **Topic:** Archiving & Compression | **Difficulty:** ⭐⭐☆☆☆
