# 📓 Progress Log

---
## Days 1-3
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

## Day 4 
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

## Day 5 
**Topics:** OSI MODEL & File permssions and Text editors
**What I did:**
- Completed OSI Model Room in TryHackMe
- Lecture on File Permissions and Text Editors
- Made an Linux command line cheat sheet
- Pactice chmod command
     
**Key learnings:**
- File permissions are very imporrtant concepts to learn
- Text editors for Bash scripting will be needed for python scripts

## Day 6
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

# Day 7 — Bash Scripting Begins 🟣

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


## Day 8 – Operating Systems Fundamentals

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

## Day 9 – Command Line & System Navigation

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

## Day 10 – Operating System Security

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

## Day 11 – Software Fundamentals

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

### Day 12: Web Application Security & Core Interception Tools

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



# Day 13: OWASP Top 10, SQL Injection, and Tool Building
**Date:** June 7, 2026

## 📚 Theory & Concepts Covered
* **OWASP Top 10 (2025) Breakdown:** Completed Module 5, Lectures 8 and 9. Focused on understanding critical web application security risks, shifting patterns in common vulnerabilities, and modern defensive strategies.
* **SQL Injection Fundamentals:** Completed the TryHackMe *SQL Injection Introduction* room (Web App Vulnerabilities I module). Studied how unsanitized user input can manipulate backend database queries.

## 🔬 Hands-on Labs & Exploitation
* **DVWA Manual Exploitation:** Practiced manual SQLi testing on Damn Vulnerable Web Application (DVWA). 
    * Utilized the classic authentication bypass payload: `' OR 1=1--`
    * **Takeaway:** Analyzed how the breaking quote (`'`) forces an early exit in the SQL syntax, while `OR 1=1` creates a condition that evaluates to true for every row, and `--` comments out the remainder of the original query.
* **PortSwigger Web Security Academy:** Successfully completed 2 additional SQLi labs (bringing the total to 4 completed labs) to practice identifying entry points and extracting data in realistic environments.

## 💻 Code & Automation (Build #2)
* **Project Name:** Automated SQLi Vulnerability Tester
* **Language:** Python
* **Functionality:** Developed a script from scratch that automates entry-point testing. The tool sends a list of common SQLi payloads to a target parameter and parses the HTTP response to detect specific database error strings (e.g., MySQL, PostgreSQL, or Oracle syntax errors).
* **Key Learnings:** Gained hands-on experience in using the `requests` library for automated payload injection and handling custom HTTP headers/parameters.


# Day 14: Website Defacement and CSRF Fundamentals
**Date:** June 8, 2026

## 📚 Theory & Concepts Covered
* **Website Defacement Practical:** Completed Module 5, Lecture 6. Explored how attackers gain unauthorized access to alter the visual appearance of a target website, the typical entry points used, and defensive remediation steps.
* **Cross-Site Request Forgery (CSRF):** Completed the TryHackMe *CSRF Introduction* room (Web App Vulnerabilities I module). 
    * **Core Concept:** Analyzed how attackers trick a victim's browser into executing unwanted actions on a trusted web application where the victim is currently authenticated.
    * **Key Mechanics:** Studied the role of session cookies, the vulnerability of state-changing requests lacking unique tokens, and how standard defensive mechanisms like SameSite cookie attributes and anti-CSRF tokens mitigate these attacks.

## 📝 Assignments & Submissions
* **Assignment 7 (Admin Panel):** Successfully completed the relevant tasks in the TryHackMe `tutedude-cybersec` room, documented the proof of compromise via screenshots, and compiled the final submission zip.
* **Assignment 8 (IDOR):** Analyzed Insecure Direct Object References within the lab environment, demonstrated the ability to access unauthorized user data by manipulating parameters, and submitted the required documentation.

## Day 15

### Tutedude
Module 5 Lec 10 — Bug Bounty Workflow Part 1 (Recon + SQL Injection)
Module 5 Lec 11 — Bug Bounty Workflow Part 2 (CSRF + RCE)

### TryHackMe
XSS Introduction [Web App Vulnerabilities I] ← carry-over from Day 13
Burp Suite Repeater [Burp Suite]
IDOR [Web App Vulnerabilities I]

### Lab
Build #3: HTTP header fuzzing tool in Python
Test fuzzer on DVWA or a local target


# Day 15 — Network VAPT: Black Box Intro 🔍
**Date:** June 20, 2026
**Roadmap Phase:** Module 6 — Black Box & Grey Box VAPT

---

## What I Covered Today

### 📚 Tutedude — Module 6, Lectures 1–3
- Introduction to Network VAPT methodology
- Black Box testing approach — zero prior knowledge of target
- Reconnaissance phases: passive and active recon
- Understanding scope, rules of engagement, and reporting basics

### 🟥 TryHackMe
- **Offensive Security Intro** — understanding the attacker mindset, ethical hacking overview
- **Defensive Security Intro** — blue team concepts, SOC, threat intelligence, SIEM basics

---

## Key Concepts

| Concept | Description |
|---------|-------------|
| Black Box Testing | Tester has zero knowledge of target infrastructure |
| Passive Recon | Gathering info without touching the target (OSINT, Shodan) |
| Active Recon | Direct interaction with target (nmap, ping sweeps) |
| Rules of Engagement | Scope boundaries defined before any test begins |
| Offensive Security | Finding vulnerabilities before attackers do |
| Defensive Security | Detecting, preventing, and responding to attacks |

---

## Key Takeaway
Black Box VAPT mirrors real-world attacker conditions — you start with nothing and build a picture of the target through methodical recon. Understanding both offensive and defensive perspectives is essential for effective pentesting.

---

*Part of my 28-day cybersecurity learning roadmap.*

---
---

# Day 16 — Metasploit + Scanning 🔫
**Date:** June 21, 2026
**Roadmap Phase:** Module 6 — Black Box & Grey Box VAPT

---

## What I Covered Today

### 📚 Tutedude — Module 6, Lectures 4–6
- Metasploit Framework architecture and components
- Understanding modules: exploits, payloads, auxiliaries, post
- Scanning with Metasploit auxiliary modules
- Setting RHOSTS, LHOST, LPORT options
- Difference between staged and stageless payloads

### 🟥 TryHackMe
- **Metasploit: The Basics** — msfconsole navigation, search, use, show options
- **Metasploit: Scanning and Exploitation** — db_nmap, auxiliary scanners, running exploits

---

## Key Concepts

| Concept | Description |
|---------|-------------|
| msfconsole | Main Metasploit interface |
| Auxiliary modules | Scanners, fuzzers, no payload needed |
| Exploit modules | Code that takes advantage of a vulnerability |
| Payload | Code executed on target after exploitation |
| Staged payload | Sends small stager first, pulls rest from attacker |
| Stageless payload | Single self-contained payload, more reliable |
| RHOSTS | Target IP address |
| LHOST | Attacker IP (your machine) |
| db_nmap | Nmap integrated into Metasploit database |

---

## Metasploit Basic Workflow
```
msfconsole
search <vulnerability>
use <module number>
show options
set RHOSTS <target IP>
set LHOST <your IP>
exploit
```

---

## Key Takeaway
Metasploit is a framework, not a magic button — understanding each component (exploit, payload, options) separately is what makes you effective with it. Staged vs stageless payload choice directly impacts reliability of shells.

---

*Part of my 28-day cybersecurity learning roadmap.*

---
---

# Day 17 — Exploitation + Shells 🐚
**Date:** June 22, 2026
**Roadmap Phase:** Module 6 — Black Box & Grey Box VAPT

---

## What I Covered Today

### 📚 Tutedude — Module 6, Lectures 7–9
- Types of shells: bind shell vs reverse shell
- Meterpreter vs command shell — differences and use cases
- Post-exploitation basics: enumeration, privilege checking
- Metasploitable 2 as a lab target — intentionally vulnerable Linux VM

### 🟥 TryHackMe
- **Shells and Listeners** — netcat listeners, reverse shells, bind shells, shell stabilization

### 🔬 Lab — Metasploitable 2 Exploitation
- Identified running services on Metasploitable 2 via nmap
- Exploited vsftpd 2.3.4 backdoor vulnerability
- Gained root shell on target
- Confirmed access with `id`, `whoami`, `hostname`

---

## Key Concepts

| Concept | Description |
|---------|-------------|
| Reverse Shell | Target connects back to attacker |
| Bind Shell | Attacker connects to listener on target |
| Meterpreter | Advanced in-memory shell, feature-rich |
| Command Shell | Raw shell, basic but reliable |
| Shell Stabilization | Making raw shells interactive (python pty) |
| vsftpd 2.3.4 | FTP backdoor planted in source code (CVE-2011-2523) |
| Metasploitable 2 | Intentionally vulnerable VM for practice |

---

## Shell Stabilization Technique
```bash
# After getting raw shell
python3 -c 'import pty;pty.spawn("/bin/bash")'
export TERM=xterm
# Ctrl+Z
stty raw -echo; fg
```

---

## vsftpd 2.3.4 Exploitation
```bash
use exploit/unix/ftp/vsftpd_234_backdoor
set RHOSTS <target>
exploit
# Result: root shell, uid=0(root) gid=0(root)
```

---

## Key Takeaway
Reverse shells are preferred in real engagements because targets rarely have inbound firewall rules blocking outbound connections. Meterpreter is powerful but a raw command shell is often more reliable — know when to use each.

---

*Part of my 28-day cybersecurity learning roadmap.*

---
---

# Day 18 — Privilege Escalation + AI Security Intro 🤖
**Date:** June 23, 2026
**Roadmap Phase:** Module 6 + Module 9 (AI Security)

---

## What I Covered Today

### 📚 Tutedude — Module 6, Lectures 10–11
- Grey Box VAPT methodology — partial knowledge of target
- Linux Privilege Escalation techniques overview
- SUID binaries, sudo misconfigurations, cron job abuse
- Difference between Black Box and Grey Box engagements

### 🟥 TryHackMe
- **Linux PrivEsc Basics** — enumeration for privesc, common attack vectors

### 📖 AI Security Reading
- **OWASP LLM Top 10** (LLM01–LLM10) — first complete read
- **Microsoft AI Red Team Blog** — first 3 posts, adversarial ML concepts

---

## Key Concepts

### Privilege Escalation

| Technique | Description |
|-----------|-------------|
| SUID binaries | Files that run as owner (root) regardless of who executes |
| Sudo misconfiguration | Commands a user can run as root via sudo |
| Cron job abuse | Writable scripts run by root on a schedule |
| Writable /etc/passwd | Manually add root user |
| Kernel exploits | Exploit unpatched kernel vulnerabilities |

### OWASP LLM Top 10 Overview

| ID | Vulnerability |
|----|--------------|
| LLM01 | Prompt Injection |
| LLM02 | Insecure Output Handling |
| LLM03 | Training Data Poisoning |
| LLM04 | Model Denial of Service |
| LLM05 | Supply Chain Vulnerabilities |
| LLM06 | Sensitive Information Disclosure |
| LLM07 | Insecure Plugin Design |
| LLM08 | Excessive Agency |
| LLM09 | Overreliance |
| LLM10 | Model Theft |

---

## Grey Box vs Black Box

| | Black Box | Grey Box |
|--|-----------|----------|
| Knowledge | Zero | Partial (credentials, architecture) |
| Time | More recon needed | Faster, targeted |
| Real world use | External attacker simulation | Authenticated user simulation |

---

## Key Takeaway
Privilege escalation is almost always the step that turns a foothold into full system compromise. OWASP LLM Top 10 maps directly to real attack surfaces on AI products — Prompt Injection (LLM01) is already appearing in bug bounty programs. This is where offensive security and AI security start to converge.

---

# Day 19 - AI Security

#### 🛠️ What I Did Today
*   **AI Red Teaming:** Completed Module 9 (Lec 1-2) covering Securing Emerging Tech and AI Red Teaming methodologies.
*   **TryHackMe Labs:** Practiced exploiting web application flaws via the **Command Injection** module.
*   **AI Security Lab (Gandalf):** Successfully attacked Lakera's **Gandalf AI Game (Level 5+)**. Documented advanced prompt injection bypass tactics (like JSON schema formatting, translation layering, and pseudo-code injection) used to defeat multi-layered LLM guardrails.
*   **Documentation & Builds:** Formulated and published my `prompt-injection-notes.md` repository on GitHub to track active exploit payloads.
*   **Community & Recon:** Signed up on HackerOne, joined the **AI Village Discord** to track open-source AI vulnerabilities, and completed a 30-minute target reconnaissance session.

#### 📈 Key Takeaway
Level 5+ guardrails cannot be beaten with simple keyword requests. Bypassing them requires breaking semantic continuity—forcing the LLM to switch contexts (e.g., treating a prompt like raw code execution or a JSON object) to bypass input/output validation firewalls.

*Part of my 28-day cybersecurity learning roadmap.*
---

