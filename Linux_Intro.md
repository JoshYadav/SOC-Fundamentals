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
