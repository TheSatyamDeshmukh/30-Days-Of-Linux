# Day 13 🔑 — SSH & Remote Access

> **"SSH = Doosre computer mein ghar baithe jaana!"**

---

## 🤔 SSH Kya Hai?

**SSH (Secure Shell)** se tum **doosre computer mein remotely login** kar sakte ho — woh computer chahe duniya ke kisi bhi kone mein ho! Sab kuch **encrypted** hota hai.

**Analogy:** Jaise WhatsApp pe baat karte ho — doosra banda door hai, par secure connection se baat ho rahi hai.

---

## 🚀 SSH Connect Karna

```bash
ssh username@ip_address           # Basic connect
ssh rahul@192.168.1.100           # Local network
ssh rahul@server.example.com      # Domain se
ssh -p 2222 rahul@192.168.1.100   # Custom port
ssh -v rahul@server               # Verbose (debug ke liye)
exit                              # Connection band karo
```

---

## 🔐 SSH Keys — Password Se Better!

Password se login = har baar type karo
SSH Key = ek baar banao, hamesha use karo — **aur zyada secure bhi!**

**Key Pair Kaise Kaam Karta Hai:**
```
Tumhara Computer          Remote Server
┌──────────────┐          ┌──────────────┐
│ Private Key  │          │ Public Key   │
│ (secret!)    │◀────────▶│ (server pe)  │
│ ~/.ssh/id_rsa│          │ ~/.ssh/      │
└──────────────┘          │ authorized   │
                          │ _keys        │
                          └──────────────┘
```

**Key Banana:**
```bash
ssh-keygen                        # Key pair banao
ssh-keygen -t ed25519             # Modern algorithm (recommended)
ssh-keygen -t rsa -b 4096         # RSA 4096-bit

# Files ban jaayengi:
# ~/.ssh/id_ed25519       ← PRIVATE KEY (kabhi share mat karo!)
# ~/.ssh/id_ed25519.pub   ← Public key (server pe jaayegi)
```

**Public Key Server Pe Bhejo:**
```bash
ssh-copy-id username@server       # Automatic way
ssh-copy-id -i ~/.ssh/id_ed25519.pub user@server

# Ya manually:
cat ~/.ssh/id_ed25519.pub         # Copy karo
# Server pe jao aur:
echo "COPIED_KEY" >> ~/.ssh/authorized_keys
```

---

## 📁 SCP — Secure File Copy

```bash
# Local → Remote
scp file.txt rahul@server:/home/rahul/

# Remote → Local
scp rahul@server:/home/rahul/file.txt ./

# Folder copy (r = recursive)
scp -r myfolder/ rahul@server:/home/rahul/

# Custom port
scp -P 2222 file.txt rahul@server:/path/
```

---

## 🔄 rsync — Smart Copy

```bash
rsync -av source/ rahul@server:/dest/      # Sync karo
rsync -av --delete source/ dest/           # Delete extra files
rsync -avz source/ rahul@server:/dest/     # Compress karo (-z)
rsync -avzn source/ dest/                  # Dry run (actual copy nahi)
```

---

## ⚙️ SSH Config File

Baar baar poora command likhna boring hai? Config file banao!

```bash
nano ~/.ssh/config
```

```
Host myserver
    HostName 192.168.1.100
    User rahul
    Port 22
    IdentityFile ~/.ssh/id_ed25519

Host production
    HostName server.example.com
    User deploy
    Port 2222
```

Ab bas:
```bash
ssh myserver              # Poori detail yaad nahi karni!
ssh production
```

---

## 🏋️ Practice (Local SSH Setup)

```bash
# OpenSSH install karo
sudo apt install openssh-server

# Service start karo
sudo systemctl start ssh
sudo systemctl enable ssh

# Status dekho
sudo systemctl status ssh

# Local se local mein connect karo (test ke liye)
ssh localhost
```

-e 
**Day:** 13/30 | **Topic:** SSH & Remote Access | **Difficulty:** ⭐⭐⭐☆☆
