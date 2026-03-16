## 💠Lesson 7: Files, Disk Usage & Suspicious Artifacts

This matters for SOC because attackers:

- Drop files
- Hide scripts
- Create unusual directories
- Fill disk space intentionally

---

## 1️⃣ `ls -lh` (Human-readable sizes)

Run:

```bash
ls -lh
```

Why:

- See file sizes clearly
- Spot unusually large files

SOC relevance:

- Large suspicious files
- Data exfiltration staging

---

## 2️⃣ `du` (Disk Usage)

Run:

```bash
du -h --max-depth=1
```

Meaning:

- Show folder sizes
- At current level

SOC relevance:

- Identify abnormal storage spikes

---

## 3️⃣ `df -h` (Disk Free)

Run:

```bash
df -h
```

Shows:

- Disk space usage

SOC relevance:

- Ransomware fills disks
- Log flooding attacks

---

## 4️⃣ `find` (VERY IMPORTANT)

This is one of the most powerful commands.

### Find files by name

Run:

```bash
find /home -name"*.sh"
```

SOC relevance:

- Find suspicious shell scripts

---

### Find recently modified files

Run:

```bash
find / -mtime -1
```

Meaning:

- Files modified in last 1 day

SOC relevance:

- Post-incident timeline

---

### Find large files

Run:

```bash
find / -type f -size +100M
```

SOC relevance:

- Detect abnormal large artifacts

---

## 5️⃣ File Type Check

Run:

```bash
file filename
```

SOC relevance:

- Check real file type
- Detect disguised executables

---

# 📘 SUMMARY TABLE

| Command | Use | Example |
| --- | --- | --- |
| `ls -lh` | Show file sizes | `ls -lh` |
| `du -h` | Directory usage | `du -h --max-depth=1` |
| `df -h` | Disk free space | `df -h` |
| `find` | Search files | `find /home -name "*.sh"` |
| `file` | Identify file type | `file test.sh` |

---

# 🎤 Interview-Ready Lines

You can say:

- “I use `find` to locate suspicious or recently modified files during investigation.”
- “Disk usage anomalies can indicate ransomware or data staging.”
- “File command helps detect disguised executables.”
