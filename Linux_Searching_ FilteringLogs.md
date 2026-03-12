## 1️⃣ Why Searching Logs Matters (SOC REALITY)

Logs are **huge**.

No SOC analyst scrolls logs manually.

SOC analysts ask:

- “Show me failed logins”
- “Show me SSH activity”
- “Show me errors from last hour”

To do this, you must **filter**.

---

## 2️⃣ `grep` — THE MOST IMPORTANT LOG TOOL

`grep` searches text for keywords.

### 🔹 Basic usage

👉 Run:

```bash
grep ssh /var/log/auth.log
```

Meaning:

- Search for the word **ssh**
- Inside `auth.log`

SOC use:

- SSH logins
- Brute-force attempts

---

### 🔹 Case-insensitive search

👉 Run:

```bash
grep -i failed /var/log/auth.log
```

SOC relevance:

- Finds “Failed”, “FAILED”, “failed”

---

### 🔹 Count matching lines

👉 Run:

```bash
grep -c failed /var/log/auth.log
```

SOC relevance:

- Detect brute-force patterns
- Alert thresholds

---

### 🔹 Search multiple words

👉 Run:

```bash
grep -E"failed|invalid" /var/log/auth.log
```

SOC relevance:

- Catch multiple attack indicators at once

---

## 3️⃣ Combining Commands (PIPE `|`) — SOC SKILL

The pipe sends output of one command to another.

### 🔹 Example

👉 Run:

```bash
ps aux | grep ssh
```

SOC relevance:

- Find SSH-related processes
- Check if sshd is running

---

## 4️⃣ `journalctl` — SYSTEMD LOGS (VERY IMPORTANT)

Modern Linux uses **systemd**.

Its logs are accessed via `journalctl`.

---

### 🔹 View all logs

👉 Run:

```bash
journalctl
```

Press:

- `q` to quit

---

### 🔹 View recent logs

👉 Run:

```bash
journalctl -n 20
```

SOC relevance:

- Last 20 events
- Incident timelines

---

### 🔹 Follow logs live

👉 Run:

```bash
journalctl -f
```

SOC relevance:

- Live monitoring during incidents

---

### 🔹 Logs for a specific service

👉 Run:

```bash
journalctl -u ssh
```

SOC relevance:

- SSH attacks
- Service abuse

---

## 5️⃣ Time-Based Filtering (CRITICAL FOR INCIDENTS)

### 🔹 Logs since today

👉 Run:

```bash
journalctl --since today
```

---

### 🔹 Logs from last 1 hour

👉 Run:

```bash
journalctl --since"1 hour ago"
```

SOC relevance:

- Incident response timelines

---

## 6️⃣ Real SOC Investigation Example

Question:

> “Did anyone try to brute-force SSH?”
> 

Commands:

```bash
grep failed /var/log/auth.log
journalctl -u ssh --since"1 hour ago"
```

This is **real SOC work**.

---

# 📘 SUMMARY TABLE (FOR NOTES & INTERVIEWS)

| Command | Use | Example | What It Actually Helps In |
| --- | --- | --- | --- |
| `grep` | Search text inside logs | `grep ssh auth.log` | Find SSH-related entries in auth log |
| `grep -i` | Case-insensitive search | `grep -i failed auth.log` | Detect failed logins regardless of case |
| `grep -c` | Count matching lines | `grep -c failed auth.log` | Count number of failed login attempts |
| `grep -E` | Multiple patterns (OR logic) | `grep -E "fail | error" auth.log` |
| `|` (pipe) | Combine commands | `cat auth.log | grep ssh` | Filter command output step-by-step |
| `journalctl` | View all systemd logs | `journalctl` | Initial broad system check |
| `journalctl -n 20` | Show last 20 entries | `journalctl -n 20` | Quick recent activity check |
| `journalctl -f` | Live log monitoring | `journalctl -f` | Monitor during active incident |
| `journalctl -u ssh` | Service-specific logs | `journalctl -u ssh` | Investigate SSH brute force |
| `journalctl --since today` | Filter by time | `journalctl --since today` | Incident timeline analysis |
| `journalctl -xe` | Recent logs with explanation | `journalctl -xe` | Troubleshooting + system errors |

## 🔍 LOG SEARCHING COMMANDS

---

## 🎤 INTERVIEW-READY LINES

Say these confidently:

- **“grep is used to filter specific events from log files.”**
- **“journalctl is used to analyze systemd-managed logs.”**
- **“SOC investigations rely on time-based log filtering.”**
- **“Pipes allow combining commands for efficient analysis.”**
