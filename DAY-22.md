# Day 22 📦 — Package Building

> **"Apna .deb package banao — pro developer ban jao!"**

---

## 🤔 Package Building Kyu?

Kabhi kabhi tumhara software package manager mein nahi hota. Khud ka `.deb` package banane se:
- Anyone easily install kar sakta hai
- Dependencies automatically handle hoti hain
- Professional distribution possible hai

---

## 📁 .deb Package Structure

```
mypackage/
├── DEBIAN/              ← Control files (zaroori!)
│   ├── control          ← Package info (naam, version, dependencies)
│   ├── postinst         ← Install ke baad chalega (optional)
│   ├── prerm            ← Remove se pehle chalega (optional)
│   └── postrm           ← Remove ke baad chalega (optional)
└── usr/
    └── local/
        └── bin/
            └── myprogram  ← Actual program
```

---

## 🔧 .deb Package Banana — Step by Step

```bash
# Step 1: Structure banao
mkdir -p mypackage/DEBIAN
mkdir -p mypackage/usr/local/bin

# Step 2: Program likhna
cat > mypackage/usr/local/bin/hello-linux << 'EOF'
#!/bin/bash
echo "Hello from my custom Linux package!"
echo "Installed by: $(whoami)"
EOF
chmod +x mypackage/usr/local/bin/hello-linux

# Step 3: Control file likhna
cat > mypackage/DEBIAN/control << 'EOF'
Package: hello-linux
Version: 1.0.0
Section: utils
Priority: optional
Architecture: amd64
Maintainer: Tumhara Naam <email@example.com>
Description: My first Linux package
 Yeh mera pehla .deb package hai!
 Linux seekhte waqt banaya.
EOF

# Step 4: Package build karo
dpkg-deb --build mypackage
# hello-linux_1.0.0.deb ban jaayega!

# Step 5: Install karo
sudo dpkg -i mypackage.deb

# Step 6: Test karo
hello-linux

# Step 7: Remove karo
sudo dpkg -r hello-linux
```

---

## 📋 control File Details

```
Package: package-naam          # lowercase, hyphens allowed
Version: 1.0.0                 # X.Y.Z format
Section: utils                 # Category
Priority: optional             # required/important/standard/optional/extra
Architecture: amd64            # amd64/i386/all/arm64
Depends: bash, python3         # Dependencies
Maintainer: Naam <email>       # Tumhara info
Homepage: https://example.com  # Website
Description: Short description # First line = short
 Long description here         # Space se indent = long desc
 More details here.
```

---

## 🏋️ Practice — Apna Package Banao

```bash
# System info script ka package banao!
mkdir -p sysinfo_pkg/DEBIAN
mkdir -p sysinfo_pkg/usr/local/bin

cat > sysinfo_pkg/usr/local/bin/sysinfo << 'EOF'
#!/bin/bash
echo "=== System Info ==="
echo "Hostname: $(hostname)"
echo "OS: $(cat /etc/os-release | grep PRETTY_NAME | cut -d= -f2 | tr -d '"')"
echo "RAM: $(free -h | grep Mem | awk '{print $2}')"
echo "Disk: $(df -h / | tail -1 | awk '{print $2}')"
EOF

chmod +x sysinfo_pkg/usr/local/bin/sysinfo

cat > sysinfo_pkg/DEBIAN/control << 'EOF'
Package: sysinfo
Version: 1.0.0
Section: utils
Priority: optional
Architecture: all
Maintainer: Your Name <you@email.com>
Description: System information tool
 Quick system info display karta hai.
EOF

dpkg-deb --build sysinfo_pkg
sudo dpkg -i sysinfo_pkg.deb
sysinfo
```

---

**Day:** 22/30 | **Topic:** Package Building | **Difficulty:** ⭐⭐⭐⭐☆
