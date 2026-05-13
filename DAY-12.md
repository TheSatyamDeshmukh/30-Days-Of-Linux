# Day 12 🌐 — Networking Basics

> **"Linux networking = internet ka asli remote control!"**

---

## 🌍 Network Concepts — Simple Bhasha Mein

**IP Address** = Tumhare ghar ka address. Jaise "Gali No. 5, House No. 12" — waise hi IP batata hai computer kahaan hai.

**Port** = Ghar ke darwaze. Ek ghar mein kai darwaze hote hain — ek darwaza Web ke liye (80), ek SSH ke liye (22), etc.

**DNS** = Phone book jaisi. `google.com` → `142.250.x.x` IP mein convert karta hai.

---

## 🔍 Network Info Dekhna

```bash
ip addr show              # IP addresses dekho (modern)
ip addr show eth0         # Specific interface
ifconfig                  # Older command (net-tools install karna padega)
hostname                  # Computer ka naam
hostname -I               # Sirf IP address
ip route show             # Routing table
cat /etc/resolv.conf      # DNS servers kaun se hain?
```

---

## 📡 Connectivity Test

```bash
ping google.com           # Internet chal raha hai?
ping -c 4 google.com      # Sirf 4 packets bhejo
ping 192.168.1.1          # Local gateway ping karo
traceroute google.com     # Packet kahaan kahaan se guzra?
curl -I https://google.com  # Website respond kar rahi hai?
wget --spider google.com  # URL check karo (download mat karo)
```

---

## 🌐 curl & wget

```bash
# curl
curl https://api.ipify.org            # Tumhara public IP
curl -O https://example.com/file.zip  # File download karo
curl -L https://example.com           # Redirects follow karo
curl -X POST -d "data=value" url      # POST request

# wget
wget https://example.com/file.zip     # File download karo
wget -O myfile.zip https://url        # Naam deke download
wget -q https://url                   # Quiet mode (no output)
wget -r https://website.com           # Poori website download (careful!)
```

---

## 🔌 Ports & Connections

```bash
ss -tulpn                 # Open ports aur connections (modern)
netstat -tulpn            # Older version
ss -tulpn | grep :80      # Port 80 kaun use kar raha hai?
lsof -i :8080             # Port 8080 ki detail
ss -s                     # Connection statistics
```

**Common Ports Yaad Karo:**
| Port | Service |
|------|---------|
| 22 | SSH |
| 80 | HTTP |
| 443 | HTTPS |
| 21 | FTP |
| 3306 | MySQL |
| 5432 | PostgreSQL |
| 6379 | Redis |
| 27017 | MongoDB |

---

## 📁 /etc/hosts — Local DNS

```bash
cat /etc/hosts            # Local DNS entries

# Sudo se edit karo:
sudo nano /etc/hosts

# Entry add karo:
# 192.168.1.100   myserver.local
# Ab "myserver.local" IP mein resolve hoga
```

---

## 🏋️ Practice

```bash
ip addr show
ping -c 3 8.8.8.8
curl https://api.ipify.org
ss -tulpn
cat /etc/resolv.conf
```

-e 
**Day:** 12/30 | **Topic:** Networking Basics | **Difficulty:** ⭐⭐⭐☆☆
