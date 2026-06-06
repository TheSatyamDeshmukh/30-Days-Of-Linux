# Day 25 🔗 — Linux Networking Advanced

> **"Ab network ka deep dive — DNS, routing, troubleshooting sab!"**

---

## 🌐 DNS — Domain Name System

```bash
# DNS resolution check karo
nslookup google.com               # Basic DNS query
dig google.com                    # Detailed DNS info
dig google.com A                  # A records (IPv4)
dig google.com AAAA               # AAAA records (IPv6)
dig google.com MX                 # Mail records
dig +short google.com             # Sirf IP
host google.com                   # Simple lookup
cat /etc/resolv.conf              # DNS servers kaun se hain?
```

---

## 🛣️ Routing

```bash
ip route show                     # Routing table
route -n                          # Older way
ip route add 10.0.0.0/8 via 192.168.1.1   # Route add karo
ip route del 10.0.0.0/8          # Route delete karo
traceroute google.com             # Packet ka path dekho
tracepath google.com              # Similar (no sudo)
mtr google.com                    # Best! Live traceroute
```

---

## 🔍 Network Troubleshooting

```bash
# Step 1: Network interface up hai?
ip link show
ip link set eth0 up               # Interface up karo

# Step 2: IP address hai?
ip addr show

# Step 3: Gateway reachable hai?
ip route show
ping -c 3 192.168.1.1             # Default gateway ping karo

# Step 4: DNS kaam kar raha hai?
ping -c 3 8.8.8.8                 # IP se (DNS bypass)
ping -c 3 google.com              # Domain se (DNS test)
nslookup google.com               # DNS directly test

# Step 5: Port open hai?
telnet server 80                  # Port 80 test
nc -zv server 80                  # netcat se test
curl -v telnet://server:80        # curl se test
```

---

## 🔌 netcat (nc) — Network Swiss Army Knife

```bash
# Port scan karo
nc -zv 192.168.1.1 80
nc -zv 192.168.1.1 1-1000        # Port range scan

# Simple server banao
nc -l 8080                        # Port 8080 pe listen karo

# Connect karo
nc server 8080                    # Server se connect

# File transfer
nc -l 8080 > received.txt         # Receiver
nc server 8080 < file.txt         # Sender
```

---

## 🔍 nmap — Port Scanner

```bash
sudo apt install nmap
nmap localhost                     # Apne open ports
nmap 192.168.1.1                  # Gateway scan
nmap -p 80,443 google.com         # Specific ports
nmap -sV 192.168.1.1              # Service version detect
nmap -A 192.168.1.1               # Aggressive scan (all info)
nmap 192.168.1.0/24               # Poora subnet scan
```

---

## 🔐 Network Security Check

```bash
ss -tulpn                         # Open ports aur processes
sudo lsof -i                      # Network connections
sudo lsof -i :80                  # Port 80 connections
arp -a                            # ARP table (local network)
```

---

## 🏋️ Practice

```bash
ip addr show
ip route show
dig google.com +short
nslookup github.com
ping -c 3 8.8.8.8
traceroute -m 5 google.com
ss -tulpn
```

---

**Day:** 25/30 | **Topic:** Networking Advanced | **Difficulty:** ⭐⭐⭐⭐☆
