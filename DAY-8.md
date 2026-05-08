# Day 8 ⚡ — Processes & Jobs

> **"Computer ek saath kai kaam karta hai — process management woh jaadu hai!"**

---

## 🤔 Process Kya Hota Hai?

Jab bhi koi program chalta hai — woh ek **process** ban jaata hai. Har process ka ek **unique ID** hota hai jise **PID (Process ID)** kehte hain.

**Analogy:** Restaurant mein har order ka ek **token number** hota hai. Waise hi har running program ka ek PID hota hai.

```
Firefox chalaaya  → PID: 1234
Terminal chalaaya → PID: 1235
VS Code chalaaya  → PID: 1236
```

---

## 👀 Processes Dekhna

### `ps` — Snapshot

```bash
ps                         # Sirf tumhare current terminal ke processes
ps aux                     # SARE processes, detail mein
ps aux | grep firefox      # Firefox chal raha hai?
ps -ef                     # Doosra format
ps -ef | grep python       # Python process dhundho
```

**`ps aux` Output Samajhna:**
```
USER    PID  %CPU %MEM    VSZ   RSS   STAT  COMMAND
rahul  1234   2.0  1.5  12345  6789   S     firefox
  ↑     ↑      ↑    ↑                  ↑       ↑
 User  ID    CPU  RAM                State   Program
```

**STAT Codes:**
```
R = Running (chal raha hai)
S = Sleeping (wait kar raha hai)
Z = Zombie (band ho gaya par entry hai)
T = Stopped (roka gaya)
```

---

### `top` — Live Monitor

```bash
top                        # Live processes dekho (q = quit)
```

**`top` Ke Andar Shortcuts:**
```
q          = Quit
k          = Kill (PID maango)
M          = Memory se sort karo
P          = CPU se sort karo
u          = Specific user ke processes
h          = Help
```

---

### `htop` — Better Live Monitor

```bash
sudo apt install htop      # Pehle install karo
htop                       # Colorful aur easy interface!
```

`htop` mein mouse bhi kaam karta hai! Process select karo, F9 dabao → kill karo.

---

## 🔫 Process Kill Karna

```bash
kill PID                   # Process ko gracefully band karo
kill -9 PID                # Force kill (stubborn process ke liye)
kill -15 PID               # SIGTERM (default — graceful)
killall firefox            # Naam se sab firefox processes band karo
pkill firefox              # pkill (aur flexible)
pkill -u rahul             # Rahul ke sab processes kill karo
```

**Common Signals:**
| Signal | Number | Matlab |
|--------|--------|--------|
| SIGTERM | 15 | "Please band ho jao" (polite) |
| SIGKILL | 9 | "ABHI band ho jao" (force) |
| SIGHUP | 1 | "Reload karo" |

---

## 🔄 Background & Foreground Jobs

### Background Mein Chalana:

```bash
sleep 100 &                # & lagao = background mein chalaao
long_command &             # Heavy kaam background mein
```

### Running Command Ko Background Mein Bhejna:

```bash
# Command chal raha hai...
Ctrl + Z                   # Pause karo (suspend)
bg                         # Background mein bhejo
```

### Background Se Foreground:

```bash
jobs                       # Background jobs list karo
fg                         # Aakhri job foreground mein laao
fg %1                      # Job number 1 foreground mein
fg %2                      # Job number 2 foreground mein
```

### Example:

```bash
sleep 200 &                # Background mein start karo
# [1] 5678

sleep 300 &                # Doosra bhi
# [2] 5679

jobs                       # List dekho
# [1]-  Running    sleep 200 &
# [2]+  Running    sleep 300 &

fg %1                      # Pehle wale ko foreground mein laao
Ctrl + C                   # Rok do
```

---

## 📊 System Resources Dekhna

```bash
free -h                    # RAM kitni hai / kitni use ho rahi
free -m                    # MB mein
vmstat                     # Virtual memory stats
uptime                     # Computer kitne time se on hai, load average
uname -a                   # System info
nproc                      # Kitne CPU cores hain?
lscpu                      # CPU ki detail info
```

---

## 🔍 Specific Process Dhundhna

```bash
pgrep firefox              # Firefox ka PID nikalo
pgrep -l python            # Naam + PID
pidof nginx                # nginx ka PID
lsof -p 1234               # PID 1234 ne kaun si files kholi hain
lsof -i :80                # Port 80 kaun use kar raha hai?
```

---

## 🏋️ Practice

```bash
# Step 1: Background process shuru karo
sleep 500 &
sleep 600 &

# Step 2: Jobs dekho
jobs

# Step 3: ps se dekho
ps aux | grep sleep

# Step 4: PID note karo aur kill karo
kill PID_YAHAN_LIKHO

# Step 5: Confirm karo
ps aux | grep sleep

# Step 6: top dekho
top
# (q dabao exit ke liye)

# Step 7: RAM check karo
free -h
```

---

## 📝 Aaj Ka Summary

✅ Process = Running program, har ek ka PID hota hai
✅ `ps aux` — sab processes snapshot
✅ `top` / `htop` — live monitor
✅ `kill PID` — process band karo
✅ `kill -9 PID` — force kill
✅ `&` — background mein chalao
✅ `Ctrl+Z` → `bg` — background mein bhejo
✅ `jobs` / `fg` — jobs manage karo
✅ `free -h` — RAM check karo

---
**Day:** 8/30 | **Topic:** Processes & Jobs | **Difficulty:** ⭐⭐⭐☆☆
