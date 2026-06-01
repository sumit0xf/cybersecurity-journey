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

---

---

*Part of my 28-day cybersecurity learning roadmap.*
---
