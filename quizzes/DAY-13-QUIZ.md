# 📝 Day 13 Quiz — SSH & Remote Access

> **Tip:** `ssh-keygen` chalao aur keys dekho `ls ~/.ssh/`! 🔑

---

## 🟢 Section A — Easy (1 point each)

**Q1.** SSH ka full form?
- A) Super Secure Host B) Secure Shell C) System Shell Host D) Server Side Host

**Q2.** SSH se connect karne ka basic command?
- A) `connect user@server` B) `ssh user@server` C) `login user@server` D) `remote user@server`

**Q3.** SSH key pair mein kya hota hai?
- A) Sirf public key B) Sirf private key C) Public key + Private key (pair) D) Password + Username

**Q4.** SSH default port kaunsa hai?
- A) 80 B) 443 C) 22 D) 3306

**Q5.** `scp` kisliye use karte hain?
- A) Screen copy B) Secure file copy — SSH ke through files transfer C) System copy D) Script copy

---

## 🟡 Section B — Medium (2 points each)

**Q6.** `ssh-keygen -t ed25519` mein `-t ed25519` ka matlab?
- A) Time limit 25 seconds B) Ed25519 algorithm se key generate karo (modern, secure) C) Edit existing key D) Terminal 25 mode

**Q7.** Private key file ki permission kya honi chahiye?
- A) 777 B) 644 C) 600 D) 755

**Q8.** `ssh-copy-id user@server` kya karta hai?
- A) SSH install karta hai B) Tumhari public key server ke `~/.ssh/authorized_keys` mein add karta hai C) Password copy karta hai D) Config copy karta hai

**Q9.** SSH config file (`~/.ssh/config`) ka kya faida?
- A) Koi faida nahi B) Har server ke liye alias/shortcut — `ssh myserver` = full command C) Passwords store karta hai D) Auto-connect karta hai

**Q10.** `scp -r folder/ user@server:/path/` mein `-r` ka matlab?
- A) Reverse copy B) Recursive — poora folder copy karo C) Remote copy D) Read-only copy

---

## 🔴 Section C — Scenario Based (3 points each)

**Q11.** SSH connect karte ho aur yeh error aata hai:
```
WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!
```
Iska kya matlab hai?
- A) Password galat hai B) Server ka SSH fingerprint change hua — possible MITM attack ya server reinstalled hua C) Network slow hai D) SSH band hai

**Q12.** Server pe password authentication band karni hai (sirf keys allowed). Kaunsi SSH config setting?
- A) `PasswordAuth = false` B) `PasswordAuthentication no` C) `DisablePassword yes` D) `KeyOnly yes`

**Q13.** `ssh -i ~/.ssh/mykey.pem ubuntu@54.1.2.3` mein `-i` ka matlab?
- A) IP address specify B) Identify mode C) Use this specific identity/key file D) Interactive mode

**Q14.** rsync se local se remote sync karne ka command?
- A) `rsync -av /local/ server:/remote/` B) `rsync -avzh /local/ user@server:/remote/` C) `sync /local user@server` D) `scp -r /local user@server:/remote/`

**Q15.** `~/.ssh/authorized_keys` file mein kya hota hai?
- A) Tumhara private key B) Server ka fingerprint C) Sab allowed users ki **public keys** D) SSH passwords

---

## 🎯 Bonus (5 points each)

**Q16.** SSH connection timeout ho jaata hai jab idle rehta hai. Fix karne ke liye SSH config mein kya add karoge (client side)?
- A) `Timeout 300` B) `ServerAliveInterval 60` (har 60 sec pe keepalive bhejo) C) `KeepAlive yes` D) `NoTimeout true`

**Q17.** Pehli baar SSH connect karte ho toh yeh dikhta hai:
```
Are you sure you want to continue connecting (yes/no)?
```
Kyun?
- A) Password confirm karna hai B) Server ka fingerprint verify karna hai — pehli baar `~/.ssh/known_hosts` mein add hoga C) Terms accept karna hai D) Yeh normal nahi hai — error hai

---

## ✅ ANSWERS

<details>
<summary>👆 Answers dekho</summary>

| Q# | Answer | Explanation |
|----|--------|-------------|
| Q1 | B | SSH = Secure Shell — encrypted remote access |
| Q2 | B | `ssh username@hostname_or_IP` |
| Q3 | C | Key pair = public (server pe) + private (tumhare paas, secret!) |
| Q4 | C | Port 22 = SSH default. Security ke liye change karna good practice |
| Q5 | B | `scp` = Secure Copy Protocol — SSH pe file transfer |
| Q6 | B | Ed25519 = modern elliptic curve algorithm. RSA se better! |
| Q7 | C | `600` = sirf owner read/write. SSH khud warn karta hai loose permissions pe |
| Q8 | B | `ssh-copy-id` = public key append karta hai `authorized_keys` mein |
| Q9 | B | Config file = shortcuts. `Host prod\n HostName 1.2.3.4\n User ubuntu` |
| Q10 | B | `-r` = recursive — directory aur contents sab copy |
| Q11 | B | Server fingerprint change = server reinstalled ya potential security issue! |
| Q12 | B | `PasswordAuthentication no` in `/etc/ssh/sshd_config` |
| Q13 | C | `-i` = identity file — specific private key specify karo |
| Q14 | B | `-a`=archive, `-v`=verbose, `-z`=compress, `-h`=human readable |
| Q15 | C | `authorized_keys` mein un logo ki public keys hain jinhe login karne dena hai |
| Q16 | B | `ServerAliveInterval 60` = har 60 sec pe keepalive packet bhejo |
| Q17 | B | TOFU (Trust On First Use) — fingerprint `known_hosts` mein save hota hai |

</details>

**Total Marks:** 50 | **Day:** 13/30 | **Topic:** SSH & Remote Access
