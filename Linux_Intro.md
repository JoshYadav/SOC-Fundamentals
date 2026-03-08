## What Linux Actually Is (No Myths)

Linux is:

- An **operating system**
- Used on:
    - Servers
    - Cloud
    - SOC environments
    - Security tools

Linux is **not**:

- A hacking OS
- Just terminal commands
- Kali Linux only

> SOC analysts don’t “hack” in Linux — they **observe, analyze, and investigate**.
> 

---

## 2️. Linux vs Windows (SOC Reality)

| Topic | Windows | Linux |
| --- | --- | --- |
| Servers | Less common | **Very common** |
| Logs | Scattered | **Centralized & readable** |
| Security tools | Limited | **Native** |
| SOC usage | Some | **Primary** |

That’s why Linux comes **before** security topics.

---

## 3️. Linux Filesystem Structure (VERY IMPORTANT)

Linux does **not** use drives like `C:` or `D:`.

Everything starts from:

```
/
```

This is called the **root directory**.

---

### 🔹 Important Directories (MEMORIZE PURPOSE, NOT PATHS)

### `/`

- Root of the filesystem
- Everything starts here

---

### `/home`

- User files live here
- Example:
    
    ```
    /home/josh
    ```
    

SOC relevance:

- User activity
- User-created files
- Suspicious scripts often found here

---

### `/etc`

- Configuration files
- System-wide settings

SOC relevance:

- Misconfigurations
- Unauthorized changes
- Malware persistence

---

### `/var`

- Variable data
- Logs live here

SOC relevance:

- **MOST IMPORTANT DIRECTORY FOR SOC**
- Logs:
    
    ```
    /var/log
    ```
    

---

### `/bin` and `/usr/bin`

- System commands
- Essential binaries

SOC relevance:

- Attackers abuse system binaries (“living off the land”)

---

### `/tmp`

- Temporary files
- Writable by everyone

SOC relevance:

- Malware staging area
- Exploit drop location

## 4. Linux Navigation Commands (CORE)

These are **non-negotiable**.

You must be comfortable with them.

---

### `pwd`

```bash
pwd
```

**Print Working Directory**

Shows:

- Where you currently are

SOC use:

- Know context before actions

---

### `ls`

```bash
ls
```

Lists files in current directory

Common usage:

```bash
ls -lls -a
```

SOC relevance:

- Identify hidden files
- Suspicious scripts

---

### `cd`

```bash
cd directory_name
```

Change directory

Examples:

```bash
cd /homecd ..cd ~
```

SOC relevance:

- Move through filesystem during investigations

---

## 5️. Absolute vs Relative Paths (IMPORTANT)

### Absolute Path

Starts from `/`

```bash
cd /var/log
```

### Relative Path

Based on current directory

```bash
cdlog
```

SOC relevance:

- Scripts
- Logs
- Automation paths

---

## 6️. Linux Is Case-Sensitive (DO NOT FORGET)

These are **different**:

```
LoglogLOG
```

SOC relevance:

- Malware hides using look-alike names
- Missed files = missed incidents

---

## 7️. Hidden Files (Security-Relevant)

Files starting with `.` are hidden.

Example:

```
.bashrc
.profile
```

View them:

```bash
ls -a
```

SOC relevance:

- Persistence mechanisms
- Backdoors
- User-level malware

## 🗂️ LINUX DIRECTORIES SUMMARY

| Directory | Use (What it is for) | Example |
| --- | --- | --- |
| `/` | Root of the entire filesystem | `/` |
| `/home` | Stores user files and folders | `/home/josh` |
| `/etc` | System-wide configuration files | `/etc/passwd` |
| `/var` | Variable data (logs, cache) | `/var/log` |
| `/bin` | Essential system commands | `/bin/ls` |
| `/usr/bin` | User-level system commands | `/usr/bin/python3` |
| `/tmp` | Temporary files (auto-cleaned) | `/tmp/malware.sh` |

📌 **SOC NOTE:**

- `/var/log` → investigations
- `/tmp` → malware staging
- `/etc` → persistence & misconfig

## 💻 LINUX COMMANDS SUMMARY

| Command | Use (What it does) | Example |
| --- | --- | --- |
| `pwd` | Shows current directory | `pwd` |
| `ls` | Lists files in directory | `ls` |
| `ls -l` | Detailed file listing | `ls -l` |
| `ls -a` | Shows hidden files | `ls -a` |
| `cd` | Change directory | `cd /var/log` |
| `cd ..` | Move one level up | `cd ..` |
| `cd ~` | Go to home directory | `cd ~` |

📌 **SOC NOTE:**

Hidden files (`.`) often indicate:

- Persistence
- Backdoors
- User-level malware
