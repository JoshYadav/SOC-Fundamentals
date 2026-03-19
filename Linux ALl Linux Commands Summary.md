# 🟩 PHASE 1 – COMPLETE LINUX COMMAND MASTER TABLE

---

## 📂 NAVIGATION & FILESYSTEM

| Command | Use | Example | Importance |
| --- | --- | --- | --- |
| `pwd` | Show current directory | `pwd` | ⭐⭐⭐ |
| `ls` | List files | `ls` | ⭐⭐⭐ |
| `ls -l` | Detailed listing | `ls -l` | ⭐⭐⭐ |
| `ls -a` | Show hidden files | `ls -a` | ⭐⭐⭐ |
| `ls -lh` | Show file sizes | `ls -lh` | ⭐⭐ |
| `cd` | Change directory | `cd /home` | ⭐⭐⭐ |
| `cd ..` | Move one level up | `cd ..` | ⭐⭐⭐ |
| `cd ~` | Go to home directory | `cd ~` | ⭐⭐ |

---

## 📁 FILE & PERMISSION MANAGEMENT

| Command | Use | Example | Importance |
| --- | --- | --- | --- |
| `chmod` | Change permissions | `chmod 755 file.sh` | ⭐⭐⭐ |
| `chown` | Change ownership | `chown user file` | ⭐⭐ |
| `file` | Identify file type | `file script.sh` | ⭐⭐ |

---

## 👤 USER & ACCOUNT INVESTIGATION

| Command | Use | Example | Importance |
| --- | --- | --- | --- |
| `whoami` | Show current user | `whoami` | ⭐⭐⭐ |
| `who` | Show logged-in users | `who` | ⭐⭐⭐ |
| `w` | Show active sessions | `w` | ⭐⭐⭐ |
| `groups` | Show user groups | `groups` | ⭐⭐ |
| `cat /etc/passwd` | List users | `cat /etc/passwd` | ⭐⭐⭐ |
| `cat /etc/group` | List groups | `cat /etc/group` | ⭐⭐⭐ |

---

## ⚙️ PROCESS MONITORING

| Command | Use | Example | Importance |
| --- | --- | --- | --- |
| `ps` | Show terminal processes | `ps` | ⭐⭐ |
| `ps aux` | Show all processes | `ps aux` | ⭐⭐⭐ |
| `top` | Live process monitoring | `top` | ⭐⭐⭐ |
| `htop` | Advanced process view | `htop` | ⭐⭐ |
| `kill` | Stop process | `kill 1234` | ⭐⭐ |

---

## 🔧 SERVICES MANAGEMENT

| Command | Use | Example | Importance |
| --- | --- | --- | --- |
| `systemctl status` | Check service status | `systemctl status ssh` | ⭐⭐⭐ |
| `systemctl start` | Start service | `sudo systemctl start ssh` | ⭐⭐ |
| `systemctl enable` | Enable at boot | `sudo systemctl enable ssh` | ⭐⭐ |
| `systemctl list-units` | List services | `systemctl list-units --type=service` | ⭐⭐ |

---

## 📜 LOG ANALYSIS (CORE SOC SKILL)

| Command | Use | Example | Importance |
| --- | --- | --- | --- |
| `cat` | View entire log | `cat syslog` | ⭐⭐ |
| `less` | Scroll logs | `less syslog` | ⭐⭐⭐ |
| `tail` | Last log entries | `tail syslog` | ⭐⭐⭐ |
| `tail -f` | Live logs | `tail -f syslog` | ⭐⭐⭐ |
| `journalctl` | View system logs | `journalctl` | ⭐⭐⭐ |
| `journalctl -n` | Recent logs | `journalctl -n 20` | ⭐⭐ |
| `journalctl -f` | Live logs | `journalctl -f` | ⭐⭐ |
| `journalctl -u` | Service logs | `journalctl -u ssh` | ⭐⭐⭐ |
| `journalctl -xe` | Error logs | `journalctl -xe` | ⭐⭐ |

---

## 🔍 SEARCHING & FILTERING

| Command | Use | Example | Importance |
| --- | --- | --- | --- |
| `grep` | Search logs | `grep ssh auth.log` | ⭐⭐⭐ |
| `grep -i` | Case-insensitive search | `grep -i failed` | ⭐⭐⭐ |
| `grep -c` | Count matches | `grep -c failed` | ⭐⭐ |
| `grep -E` | Multiple patterns | `grep -E "fail | invalid"` |
| | | (pipe) | Combine commands | `ps aux | grep ssh` |

---

## 🌐 NETWORKING COMMANDS

| Command | Use | Example | Importance |
| --- | --- | --- | --- |
| `ss -l` | Listening sockets | `ss -l` | ⭐⭐ |
| `ss -tuln` | Open ports | `ss -tuln` | ⭐⭐⭐ |
| `ss -tulpn` | Ports + process | `ss -tulpn` | ⭐⭐⭐ |
| `ip a` | Show IP address | `ip a` | ⭐⭐⭐ |
| `ip route` | Show routing table | `ip route` | ⭐⭐ |

---

## 💾 DISK & FILE INVESTIGATION

| Command | Use | Example | Importance |
| --- | --- | --- | --- |
| `du -h` | Folder size | `du -h` | ⭐⭐ |
| `df -h` | Disk usage | `df -h` | ⭐⭐⭐ |
| `find` | Search files | `find /home -name "*.sh"` | ⭐⭐⭐ |
| `find -mtime` | Recent files | `find / -mtime -1` | ⭐⭐ |
| `find -size` | Large files | `find / -size +100M` | ⭐⭐ |

---

## 🔐 PRIVILEGE & SECURITY CHECKS

| Command | Use | Example | Importance |
| --- | --- | --- | --- |
| `grep sudo` | Check sudo logs | `grep sudo auth.log` | ⭐⭐⭐ |
| `crontab -l` | Check persistence tasks | `crontab -l` | ⭐⭐⭐ |

---

## 🧠 HISTORY & OPEN FILES (FINAL ADD-ON)

| Command | Use | Example | Importance |
| --- | --- | --- | --- |
| `history` | Show command history | `history` | ⭐⭐ |
| `lsof -i` | Show open connections | `lsof -i` | ⭐⭐ |

---

## ✏️ TEXT EDITORS

| Command | Use | Example | Importance |
| --- | --- | --- | --- |
| `nano` | Easy editing | `nano file.txt` | ⭐⭐ |
| `vim` | Advanced editor | `vim file.txt` | ⭐⭐ |
