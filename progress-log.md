# 📓 Progress Log

---
## Days 1–8 — 20/05/2026 to 27/05/2026
**Topics:** Python fundamentals + Linux CLI basics
**What I did:**
- Completed Python basics through CodeWithHarry
  - Variables, data types, conditionals, loops
  - Functions — solved all exercises independently
  - String methods
  - File I/O (reading and writing files)
  - Libraries (standard library basics)
- Completed NetworkChuck's Linux for begineers series    
  - Set up Kali Linux on VirtualBox (4GB RAM)
  - Ran first Linux terminal commands
  - Had some problems with chmod command like chmod777
  - Troubleshot `ip a` output, path-dependent `cat` usage

**Key learnings:**
- Python functions reduce repetition — solved all problems without help
- File I/O lets scripts interact with real data outside the program
- Daily practice of command line
  
---

## Day 9 — 28/05/2026
**Topics:** GitHub setup & learning roadmap finalization
**What I did:**
- Created GitHub repo `cybersecurity-journey`
- Wrote full README.md with AI security roadmap
- Set up progress-log.md and CTF writeup template
- Finalized 28-day daily learning plan
- started THM pre-security path
- completed till Intro to Lans
  
**Key learnings:**
- Network Fundamentals
- How to structure a security portfolio on GitHub
- Commit messages, branches

## Day 10 
**Topics:** OSI MODEL & File permssions and Text editors
**What I did:**
- Completed OSI Model Room in TryHackMe
- Lecture on File Permissions and Text Editors
- Made an Linux command line cheat sheet
- Pactice chmod command
     
**Key learnings:**
- File permissions are very imporrtant concepts to learn
- Text editors for Bash scripting will be needed for python scripts

## Day 11
**Topics:** Essential linux file management commands & Packets and frames
**What I did:**
- Packets and frames room
- And network fundamentals part 1
- Practice of linux file management commands
- grep & find commands are essential to find specific files
- also did research on metasploitable 2

  **key learnings:**
- Get comfortable with TCP/IP & UDP/IP
- How files are managed on linux
- Ports 101 very important

# Day 12 — Bash Scripting Begins 🟣

**Roadmap Phase:**  — Linux & Python Fundamentals

---

## What I Covered Today

### 📚 Tutedude — Module 3, Lectures 5 & 6
- Bash scripting fundamentals
- Variables, echo, and command substitution
- For loops and directory manipulation

### 🟥 TryHackMe — Pre-Security Path
- Completed: **Extending Your Network** room
- Topics: network extension concepts, VPNs, and network protocols

---

## Lab — Scripts Written in Kali Linux

### Script 1 — Variables & Echo (`variables.sh`)
```bash
#!/bin/bash
name="Sumit"
echo "Hello $name"
echo "Today is $(date)"
```
**What I learned:**
- Declaring and using variables with `$`
- `$(command)` syntax for command substitution inside a string

---

### Script 2 — For Loop (`loop.sh`)
```bash
#!/bin/bash
for i in 1 2 3 4 5
do
  mkdir "folder_$i"
  echo "Created folder_$i"
done
ls
rm -rf folder_*
echo "Cleaned up!"
```
**What I learned:**
- `for` loop syntax in bash
- Creating multiple directories dynamically using a loop variable
- Cleaning up with `rm -rf` and wildcard `*`

---

## Key Concepts

| Concept | Syntax | Example |
|---------|--------|---------|
| Variable declaration | `name="value"` | `name="Sumit"` |
| Variable usage | `$name` | `echo $name` |
| Command substitution | `$(command)` | `$(date)` |
| For loop | `for i in ... do ... done` | See Script 2 |
| Make executable | `chmod +x file.sh` | `chmod +x script.sh` |
| Run script | `./file.sh` | `./script.sh` |


## Day 13 – Operating Systems Fundamentals

### TryHackMe

* Completed: DNS in detail

### Practical Commands

```bash
ps aux
top
htop
```

### Tutedude

* Module 4 completed:

  * Information Gathering (Active & Passive)
  * Common Threat Vectors: Malicious Code and Phishing
  * Modern Attack Methodologies: From Social to Technical

### Assignments

* Assignment 1 (Basic Linux Commands) ✅ Approved
* Assignment 2 (Linux Permissions) ✅ Approved
* Assignment 3 (File System Commands) ✅ Approved
* Assignment 4 (Bash Scripting) ✅ Approved
* Assignment 5 (Information Gathering) ⏳ Pending

---

## Day 14 – Command Line & System Navigation

### TryHackMe

* Completed: HTTP in detail

### Key Concepts Learned

* Linux command line navigation
* Windows command line navigation
* File management
* System administration basics

### Practical Revision

```bash
find
grep
chmod
nano
vim
```

### Realization

Understanding the command line is critical because most cybersecurity work happens in terminals rather than graphical interfaces.

---

## Day 15 – Operating System Security

### TryHackMe

* Completed: How websites work

### Key Concepts Learned

* Authentication vs Authorization
* Least Privilege Principle
* User Accounts and Permissions
* Linux Security Concepts
* Windows Security Concepts

### Security Perspective

Misconfigured permissions remain one of the most common privilege escalation vectors in real-world environments.

---

## Day 16 – Software Fundamentals

### TryHackMe

* Completed: Putting it all together

### Python Practice

Built a DNS Lookup Utility:

```python
import socket

host = input("Target: ")

try:
    print(socket.gethostbyname(host))
except:
    print("Invalid host")
```

---

## Projects Built So Far

### Project 1 – TCP Port Scanner

* Built using Python sockets
* Scans target hosts for open ports

### Project 2 – Threaded TCP Port Scanner

* Implemented ThreadPoolExecutor
* Significantly improved scan speed

### Project 3 – DNS Lookup Tool

* Resolves domain names to IP addresses
* Uses Python socket library

### Bash Projects

* Folder Creation Automation Script
* Network Ping Script
* Secret Reader Script

---

## Current Progress

### TryHackMe

* Pre-Security Path: 50% Complete

Completed Sections:

* Introduction to Cyber Security
* Network Fundamentals
* How The Web Works

### Tutedude

* Modules 1–4 Completed
* Assignments 1–4 Approved
* Assignment 5 Pending

### Day 11: Web Application Security & Core Interception Tools

#### 📚 Theory & Concepts Learned
* **Web App Security Foundations:** Finished Tutedude Module 5 (Lectures 3 & 7) focusing on how data moves between web clients and backend servers.
* **Authentication & Parameters:** Learned how web forms use hidden parameter names (like `uname`, `submit`) to send user data to the backend.
* **Vulnerability Mechanics:** Deep-dived into the mechanics of **SQL Injection (SQLi)** and how special characters (like `'` and `--`) alter backend database queries.

#### 🛠️ Practical Skills & Hands-On Labs
* **Burp Suite Proficiency:** Configured and mastered traffic interception, modifying parameters, and forwarding raw HTTP requests using Burp's built-in browser and **Repeater** module.
* **PortSwigger Web Academy - Completed:**
    1.  *Lab 1 (SQLi in WHERE clause):* Successfully bypassed a product filter category using the payload `' OR 1=1--` to retrieve hidden/unreleased database records.
    2.  *Lab 2 (SQLi Login Bypass):* Exploited a vulnerable login mechanism using the payload `administrator'--` to completely comment out the password check and hijack the admin account.
* **TryHackMe:** Completed the final Pre-Security path checkpoint (**'Become a Defender'** room). Officially cleared for the Junior Penetration Tester path.

#### 💻 Automation & Scripting
* **Python Exploitation Tooling:** Analyzed and debugged a custom multi-payload login tester using the Python `requests` library. Understood how loops feed automated payloads into target `form_data` structures to scale vulnerability scanning.


---

*Part of my 28-day cybersecurity learning roadmap.*
---
