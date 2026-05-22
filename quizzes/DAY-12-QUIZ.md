# 📝 Day 12 Quiz — Networking Basics

> **Tip:** `ip addr show` aur `ping -c 3 8.8.8.8` chalao pehle! 🌐

---

## 🟢 Section A — Easy (1 point each)

**Q1.** `ping google.com` kisliye use karte hain?
- A) Google search karna B) Internet connectivity test karna C) Google ka IP dhundhna D) B aur C dono

**Q2.** IP address kya hota hai?
- A) Internet Password B) Computer ka network address — unique identifier C) Internet Protocol D) B aur C dono

**Q3.** `ip addr show` kya dikhata hai?
- A) IP address of google B) System ke network interfaces aur unke IP addresses C) Internet speed D) Network errors

**Q4.** Port 22 kis service ke liye use hota hai?
- A) HTTP B) HTTPS C) SSH D) FTP

**Q5.** `curl https://api.ipify.org` kya karta hai?
- A) File download karta hai B) Tumhara public IP address dikhata hai C) curl install karta hai D) API create karta hai

---

## 🟡 Section B — Medium (2 points each)

**Q6.** `ping -c 4 8.8.8.8` mein `-c 4` ka kya matlab hai?
- A) 4 second wait karo B) Sirf 4 packets bhejo phir band karo C) 4 times faster D) 4 KB data bhejo

**Q7.** DNS kya karta hai?
- A) Internet speed measure karta hai B) Domain name (google.com) ko IP address (142.x.x.x) mein convert karta hai C) Data encrypt karta hai D) Network secure karta hai

**Q8.** `ss -tulpn` mein flags ka matlab?
- A) Show, TCP, UDP, Listening, Process, Numeric ports B) System, Total, Users, Linux, Ports, Network C) Server, Test, Unix, Log, Protocol, Names D) Koi matlab nahi, default flags hain

**Q9.** `wget` aur `curl` mein basic fark?
- A) Koi fark nahi B) `wget` file download ke liye better, `curl` API requests aur data transfer ke liye flexible C) `wget` newer hai D) `curl` sirf Linux pe kaam karta hai

**Q10.** `/etc/resolv.conf` mein kya hota hai?
- A) Network passwords B) DNS server addresses C) IP routing table D) Network interface config

---

## 🔴 Section C — Hard (3 points each)

**Q11.** `traceroute google.com` kya dikhata hai?
- A) Google ka source code B) Packet ka har hop — source se destination tak ka route C) Network speed D) Google ke servers

**Q12.** `ss -tulpn | grep :80` kya dhundhta hai?
- A) Port 80 pe listening process B) 80 network connections C) 80 bytes wali packets D) HTTP headers

**Q13.** Localhost ka IP address kya hota hai?
- A) 192.168.1.1 B) 10.0.0.1 C) 127.0.0.1 D) 0.0.0.0

**Q14.** `/etc/hosts` file kisliye use hoti hai?
- A) Host party planning! B) Local DNS — IP ko domain name se map karo bina DNS server ke C) Network passwords D) Firewall rules

**Q15.** `netstat` deprecated ho raha hai — iska modern replacement?
- A) `ipstat` B) `ss` C) `network` D) `netinfo`

---

## 🎯 Bonus (5 points each)

**Q16.** Server pe website nahi khul raha. Network troubleshoot karne ke steps sahi order mein?
- A) Seedha server restart karo B) `ping IP` → `ping domain` → `ss -tulpn | grep :80` → `curl localhost` → logs check C) DNS change karo D) Firewall band karo

**Q17.** `curl -O https://example.com/file.zip` mein `-O` ka matlab?
- A) Output to screen B) File ko original naam se save karo C) Overwrite existing D) Offline mode

---

## ✅ ANSWERS

<details>
<summary>👆 Answers dekho</summary>

| Q# | Answer | Explanation |
|----|--------|-------------|
| Q1 | D | `ping` connectivity test karta hai aur IP bhi show hota hai |
| Q2 | D | IP = Internet Protocol address — network pe unique identifier |
| Q3 | B | `ip addr show` = network interfaces, MAC, IP sab |
| Q4 | C | Port 22 = SSH. 80=HTTP, 443=HTTPS, 21=FTP |
| Q5 | B | `ifconfig.me` ya `api.ipify.org` = public IP APIs |
| Q6 | B | `-c count` = count packets ke baad stop. Default = infinite |
| Q7 | B | DNS = Domain Name System — phone book of internet |
| Q8 | A | `-t`=TCP, `-u`=UDP, `-l`=listening, `-p`=process, `-n`=numeric |
| Q9 | B | `wget` = download files. `curl` = transfers data, API calls, more flexible |
| Q10 | B | `nameserver 8.8.8.8` — DNS server IP yahan hota hai |
| Q11 | B | traceroute = path trace — each router/hop dikhata hai with latency |
| Q12 | A | Port 80 (HTTP) pe kaunsi service listen kar rahi hai |
| Q13 | C | 127.0.0.1 = loopback = localhost = tumhara khud ka computer |
| Q14 | B | `/etc/hosts` = local DNS override. `127.0.0.1 mysite.local` add karo |
| Q15 | B | `ss` = Socket Statistics — `netstat` ka modern replacement |
| Q16 | B | Systematic troubleshooting: connectivity → DNS → port → service → logs |
| Q17 | B | `-O` (capital O) = Output file with remote filename |

</details>

**Total Marks:** 50 | **Day:** 12/30 | **Topic:** Networking Basics
