# Linux Commands Cheat Sheet

A quick reference for essential Linux commands.

---

## Navigation

| Command | Description | Example |
|---------|-------------|---------|
| `pwd` | Print current directory | `pwd` |
| `ls` | List files | `ls -la` |
| `cd` | Change directory | `cd /home/user` |
| `cd ..` | Go one level back | `cd ..` |
| `cd ~` | Go to home directory | `cd ~` |
| `cd -` | Go to previous directory | `cd -` |

---

## File & Directory Management

| Command | Description | Example |
|---------|-------------|---------|
| `touch` | Create empty file | `touch file.txt` |
| `mkdir` | Create directory | `mkdir myfolder` |
| `mkdir -p` | Create nested dirs | `mkdir -p a/b/c` |
| `cp` | Copy file | `cp file.txt backup.txt` |
| `cp -r` | Copy directory | `cp -r dir1 dir2` |
| `mv` | Move or rename | `mv old.txt new.txt` |
| `rm` | Remove file | `rm file.txt` |
| `rm -r` | Remove directory | `rm -r myfolder` |
| `rm -rf` | Force remove (careful!) | `rm -rf myfolder` |
| `rmdir` | Remove empty directory | `rmdir emptydir` |

---

## Viewing Files

| Command | Description | Example |
|---------|-------------|---------|
| `cat` | Print file contents | `cat file.txt` |
| `less` | Scroll through file | `less file.txt` |
| `more` | Page through file | `more file.txt` |
| `head` | First 10 lines | `head file.txt` |
| `head -n` | First N lines | `head -n 5 file.txt` |
| `tail` | Last 10 lines | `tail file.txt` |
| `tail -f` | Follow live output | `tail -f log.txt` |
| `wc` | Word/line count | `wc -l file.txt` |

---

## Searching

| Command | Description | Example |
|---------|-------------|---------|
| `grep` | Search text in file | `grep "error" log.txt` |
| `grep -r` | Search recursively | `grep -r "def" ./src` |
| `grep -i` | Case-insensitive | `grep -i "hello" file.txt` |
| `find` | Find files by name | `find . -name "*.txt"` |
| `find` | Find by type | `find . -type d` |
| `locate` | Fast file search | `locate file.txt` |

---

## Permissions

| Command | Description | Example |
|---------|-------------|---------|
| `chmod` | Change permissions | `chmod 755 script.sh` |
| `chmod u+x` | Add execute for owner | `chmod u+x script.sh` |
| `chown` | Change owner | `chown user file.txt` |
| `chown user:group` | Change owner & group | `chown user:group file.txt` |
| `chgrp` | Change group | `chgrp devs file.txt` |
| `ls -l` | View permissions | `ls -l` |
| `umask` | Default permission mask | `umask 022` |

### Permission values

```
rwx = 7   rw- = 6   r-x = 5   r-- = 4
-wx = 3   -w- = 2   --x = 1   --- = 0
```

```
chmod 755  →  rwxr-xr-x   (common for executables)
chmod 644  →  rw-r--r--   (common for files)
chmod 700  →  rwx------   (private to owner)
chmod 777  →  rwxrwxrwx   (everyone, avoid in production)
```

---

## Processes

| Command | Description | Example |
|---------|-------------|---------|
| `ps` | List processes | `ps aux` |
| `top` | Live process monitor | `top` |
| `htop` | Better process monitor | `htop` |
| `kill` | Kill by PID | `kill 1234` |
| `kill -9` | Force kill | `kill -9 1234` |
| `killall` | Kill by name | `killall firefox` |
| `jobs` | List background jobs | `jobs` |
| `bg` | Send job to background | `bg %1` |
| `fg` | Bring job to foreground | `fg %1` |
| `&` | Run in background | `./script.sh &` |
| `Ctrl + C` | Stop current process | — |
| `Ctrl + Z` | Suspend current process | — |

---

## Networking

| Command | Description | Example |
|---------|-------------|---------|
| `ping` | Test connectivity | `ping google.com` |
| `ip a` | Show IP addresses | `ip a` |
| `ifconfig` | Network interfaces | `ifconfig` |
| `curl` | Make HTTP request | `curl https://example.com` |
| `wget` | Download file | `wget https://example.com/file.zip` |
| `netstat` | Network connections | `netstat -tuln` |
| `ss` | Socket stats (modern netstat) | `ss -tuln` |
| `nmap` | Port scanner | `nmap 192.168.1.1` |
| `traceroute` | Trace packet path | `traceroute google.com` |
| `ssh` | Connect to remote host | `ssh user@192.168.1.1` |
| `scp` | Copy over SSH | `scp file.txt user@host:/path` |

---

## Disk & System Info

| Command | Description | Example |
|---------|-------------|---------|
| `df -h` | Disk space usage | `df -h` |
| `du -sh` | Directory size | `du -sh myfolder` |
| `free -h` | RAM usage | `free -h` |
| `uname -a` | System/kernel info | `uname -a` |
| `uptime` | System uptime & load | `uptime` |
| `whoami` | Current user | `whoami` |
| `who` | Logged-in users | `who` |
| `id` | User & group IDs | `id` |
| `hostname` | Machine hostname | `hostname` |
| `lscpu` | CPU info | `lscpu` |
| `lsblk` | Block devices / disks | `lsblk` |

---

## Users & Groups

| Command | Description | Example |
|---------|-------------|---------|
| `adduser` | Create new user | `sudo adduser sumit` |
| `passwd` | Change password | `passwd sumit` |
| `deluser` | Delete user | `sudo deluser sumit` |
| `usermod -aG` | Add user to group | `sudo usermod -aG sudo sumit` |
| `groups` | Show user's groups | `groups sumit` |
| `su` | Switch user | `su sumit` |
| `sudo` | Run as superuser | `sudo apt update` |
| `visudo` | Edit sudoers file | `sudo visudo` |

---

## Package Management

### Debian / Ubuntu (apt)

| Command | Description |
|---------|-------------|
| `sudo apt update` | Refresh package list |
| `sudo apt upgrade` | Upgrade all packages |
| `sudo apt install pkg` | Install a package |
| `sudo apt remove pkg` | Remove a package |
| `sudo apt autoremove` | Remove unused deps |
| `apt search pkg` | Search for a package |
| `apt show pkg` | Show package details |

### Arch / Kali (pacman)

| Command | Description |
|---------|-------------|
| `sudo pacman -Syu` | Update system |
| `sudo pacman -S pkg` | Install a package |
| `sudo pacman -R pkg` | Remove a package |
| `pacman -Ss pkg` | Search for a package |

---

## Redirection & Pipes

| Operator | Description | Example |
|----------|-------------|---------|
| `>` | Redirect output (overwrite) | `echo "hi" > file.txt` |
| `>>` | Redirect output (append) | `echo "hi" >> file.txt` |
| `<` | Redirect input | `sort < file.txt` |
| `\|` | Pipe output to command | `ls \| grep ".txt"` |
| `2>` | Redirect stderr | `cmd 2> error.log` |
| `&>` | Redirect stdout + stderr | `cmd &> all.log` |
| `/dev/null` | Discard output | `cmd > /dev/null` |

---

## Compression & Archives

| Command | Description | Example |
|---------|-------------|---------|
| `tar -czvf` | Create .tar.gz | `tar -czvf out.tar.gz folder/` |
| `tar -xzvf` | Extract .tar.gz | `tar -xzvf out.tar.gz` |
| `zip` | Create zip | `zip archive.zip file.txt` |
| `unzip` | Extract zip | `unzip archive.zip` |
| `gzip` | Compress file | `gzip file.txt` |
| `gunzip` | Decompress .gz | `gunzip file.txt.gz` |

---

## Text Processing

| Command | Description | Example |
|---------|-------------|---------|
| `echo` | Print text | `echo "Hello"` |
| `sort` | Sort lines | `sort file.txt` |
| `uniq` | Remove duplicate lines | `uniq file.txt` |
| `cut` | Cut columns | `cut -d',' -f1 file.csv` |
| `awk` | Pattern processing | `awk '{print $1}' file.txt` |
| `sed` | Stream editor | `sed 's/old/new/g' file.txt` |
| `tr` | Translate characters | `tr 'a-z' 'A-Z' < file.txt` |
| `diff` | Compare two files | `diff file1.txt file2.txt` |

---

## Shortcuts & Tips

| Shortcut | Description |
|----------|-------------|
| `Ctrl + C` | Kill running process |
| `Ctrl + Z` | Suspend process |
| `Ctrl + D` | Logout / EOF |
| `Ctrl + L` | Clear terminal |
| `Ctrl + A` | Go to start of line |
| `Ctrl + E` | Go to end of line |
| `Ctrl + R` | Search command history |
| `!!` | Repeat last command |
| `!cmd` | Repeat last `cmd` command |
| `Tab` | Autocomplete |
| `↑ / ↓` | Browse command history |
| `history` | Show command history |
| `clear` | Clear screen |
| `man cmd` | Manual for a command |
| `cmd --help` | Quick help for command |

---

## Useful One-Liners

```bash
# Find all .py files and count lines
find . -name "*.py" | xargs wc -l

# Show top 10 largest files in current dir
du -sh * | sort -rh | head -10

# Live monitor a log file
tail -f /var/log/syslog

# Check which process is using port 80
sudo ss -tulpn | grep :80

# Recursively find and replace text in files
grep -rl "old_text" . | xargs sed -i 's/old_text/new_text/g'

# Copy SSH public key to remote server
ssh-copy-id user@remote_host

# Create and enter directory in one line
mkdir newdir && cd newdir
```

---

*For cybersecurity-specific commands (nmap, netcat, Metasploit, etc.) see the dedicated pentesting cheat sheet.*
