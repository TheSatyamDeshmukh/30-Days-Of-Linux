# Day 11 🚀 — Shell Scripting: Advanced

> **"Ab asli scripts likhenge — jo real kaam karti hain!"**

---

## 🔧 Functions

```bash
#!/bin/bash

# Function define karo
greet() {
    echo "Hello, $1!"
    echo "Welcome to Linux!"
}

calculate() {
    local result=$(( $1 + $2 ))   # local = sirf function ke andar
    echo "Sum: $result"
    return $result
}

# Call karo
greet "Rahul"
greet "Priya"
calculate 10 20
```

---

## 📋 Arrays

```bash
#!/bin/bash

# Array banana
fruits=("Apple" "Banana" "Mango" "Orange")

# Element access karo
echo ${fruits[0]}          # Apple (index 0 se shuru!)
echo ${fruits[2]}          # Mango

# Sab elements
echo ${fruits[@]}

# Array ka size
echo ${#fruits[@]}

# Loop mein use karo
for fruit in "${fruits[@]}"; do
    echo "Fruit: $fruit"
done

# Element add karo
fruits+=("Grapes")
echo ${fruits[@]}
```

---

## ⚠️ Error Handling

```bash
#!/bin/bash

# set -e = koi bhi command fail ho toh script band karo
set -e

# set -u = undefined variable pe error do
set -u

# Pichli command successful thi?
ls /nonexistent 2>/dev/null
if [ $? -ne 0 ]; then
    echo "Error: File nahi mili!"
    exit 1
fi

# || ka use
mkdir /tmp/mydir || echo "Directory banane mein error!"

# Trap — script band hone pe kuch karo
trap "echo 'Script band ho gayi!'; cleanup" EXIT
```

---

## 📨 Arguments

```bash
#!/bin/bash
# ./script.sh Rahul 25 Delhi

echo "Script ka naam: $0"
echo "Pehla argument: $1"
echo "Doosra argument: $2"
echo "Teesra argument: $3"
echo "Total arguments: $#"
echo "Sab arguments: $@"

# Arguments check karo
if [ $# -lt 2 ]; then
    echo "Usage: $0 <naam> <umar>"
    exit 1
fi

naam=$1
umar=$2
echo "Hello $naam, tumhari umar $umar saal hai!"
```

---

## 📁 File Operations Script

```bash
#!/bin/bash
# Backup script

SOURCE="/home/rahul/Documents"
BACKUP="/home/rahul/backups"
DATE=$(date +%Y-%m-%d)

# Backup folder banao
mkdir -p "$BACKUP"

# Backup lo
cp -r "$SOURCE" "$BACKUP/Documents_$DATE"

echo "Backup complete: $BACKUP/Documents_$DATE"
echo "Size: $(du -sh $BACKUP/Documents_$DATE | cut -f1)"
```

---

## 🔁 Case Statement

```bash
#!/bin/bash

read -p "Kya karna hai? (start/stop/status): " action

case $action in
    start)
        echo "Service start kar raha hoon..."
        ;;
    stop)
        echo "Service band kar raha hoon..."
        ;;
    status)
        echo "Service ki status check kar raha hoon..."
        ;;
    restart)
        echo "Restart kar raha hoon..."
        ;;
    *)
        echo "Invalid option! start/stop/status/restart use karo."
        exit 1
        ;;
esac
```

---

## 📊 Real World Script — System Info

```bash
#!/bin/bash

echo "========================================="
echo "          SYSTEM INFORMATION"
echo "========================================="
echo ""
echo "Hostname     : $(hostname)"
echo "OS           : $(cat /etc/os-release | grep PRETTY_NAME | cut -d= -f2 | tr -d '"')"
echo "Kernel       : $(uname -r)"
echo "Uptime       : $(uptime -p)"
echo "Current User : $(whoami)"
echo ""
echo "--- CPU ---"
echo "CPU          : $(lscpu | grep 'Model name' | cut -d: -f2 | xargs)"
echo "Cores        : $(nproc)"
echo ""
echo "--- Memory ---"
free -h | grep Mem | awk '{print "Total: "$2, "| Used: "$3, "| Free: "$4}'
echo ""
echo "--- Disk ---"
df -h / | tail -1 | awk '{print "Total: "$2, "| Used: "$3, "| Free: "$4, "| Use%: "$5}'
echo ""
echo "========================================="
```

---

## 🏋️ Practice

Script banao jo:
1. User se folder ka path maange
2. Check kare folder exist karta hai ya nahi
3. Agar hai toh — kitni files hain, total size kya hai
4. Agar nahi hai toh — banana chahoge? (y/n)

---

**Day:** 11/30 | **Topic:** Shell Scripting Advanced | **Difficulty:** ⭐⭐⭐⭐☆
