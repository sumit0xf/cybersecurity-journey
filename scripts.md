# 🛠️ Security Scripts

Personal collection of offensive security scripts built from scratch.
Built using the build-before-tools learning method — understand the 
primitive before using the industry tool.

---

## 📁 Scripts

### 1. tcp_scanner.py
**What it does:** Scans a target IP for open TCP ports using raw sockets.  
**Concept:** TCP three-way handshake — if connect_ex() returns 0, port is open.  
**Industry tool equivalent:** Nmap  
**Key learning:** Single-threaded scanner misses nothing but is slow. 
Threading (withthreads.py) runs 100 checks in parallel.

**Usage:**
```import socket

target = "192.168.0.104"
ports = [21,22,23,80,443,3306,8080]

print(f"Scanning {target}...")
for port in ports:
    sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    sock.settimeout(1)
    result = sock.connect_ex((target, port))
    if result == 0:
        print(f"[OPEN] Port {port}")
    else:
        print(f"[DOWN] Port {port}")
    sock.close()  
```
# This script onnly scans the ports that are given 
# To scan all ports we need to use threading that scans 100 ports at a time
