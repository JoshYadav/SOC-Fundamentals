## Lesson 3: Processes, Services & Monitoring (VERY IMPORTANT)

This lesson teaches you **how Linux is actually running**.

SOC analysts **don’t guess** — they observe processes.

---

## 1️⃣ What Is a Process (CORE CONCEPT)

A **process** is:

- A program currently running in memory

Examples:

- Browser
- Terminal
- System services
- Malware (also a process)

SOC reality:

> If something malicious is running, it is **always a process**.
> 

---

## 2️⃣ What Is a Service (IMPORTANT DIFFERENCE)

A **service** is:

- A background process
- Starts automatically
- Runs continuously

Examples:

- SSH
- Network manager
- Logging services

SOC relevance:

- Attackers hide malware as **fake services**
- Persistence often = service abuse

---

## 3️⃣ Viewing Running Processes

### 🔹 Command 1: `ps`

👉 Run this:

```bash
ps
```

What it shows:

- Processes started by your terminal

Not enough for SOC — but good to understand basics.

---

### 🔹 Command 2: `ps aux` (IMPORTANT)

👉 Run this:

```bash
ps aux
```

What it shows:

- **ALL running processes**
- Who owns them
- CPU & memory usage

SOC relevance:

- Unknown processes
- Suspicious users
- High resource usage

---

## 4️⃣ Real-Time Process Monitoring

### 🔹 Command 3: `top`

👉 Run this:

```bash
top
```

What you’ll see:

- Live process list
- CPU & memory usage
- Updated continuously

Press:

- `q` → quit

SOC relevance:

- Spot malware consuming resources
- Identify suspicious spikes

---

## 5️⃣ More User-Friendly Monitoring

### 🔹 Command 4: `htop` (if available)

👉 First install it:

```bash
sudo apt updatesudo apt install htop
```

👉 Then run:

```bash
htop
```

Why this matters:

- Color-coded
- Easy to read
- Widely used by analysts

SOC relevance:

- Fast investigations
- Process hierarchy visibility

---

## 6️⃣ Process IDs (PID)

Every process has a **PID**.

SOC relevance:

- Logs reference PIDs
- Killing a process requires PID
- Correlating activity = PID-based

---

## 7️⃣ Stopping a Process (CONTROLLED)

### 🔹 Command 5: `kill`

👉 Example (DO NOT RANDOMLY KILL):

```bash
kill PID
```

SOC relevance:

- Containment action
- Stopping malicious activity

⚠️ Never kill system processes blindly.

---

## 8️⃣ Services & systemctl (SOC CRITICAL)

Linux uses `systemd`.

### 🔹 Command 6: List services

👉 Run:

```bash
systemctl list-units --type=service
```

SOC relevance:

- Detect unknown services
- Identify persistence

---

### 🔹 Command 7: Check service status

👉 Example:

```bash
systemctl status ssh
```

SOC relevance:

- Is a service running?
- Was it restarted?
- When did it start?

---

## 🚨 REAL SOC RED FLAGS (READ CAREFULLY)

Things you’ll investigate later:

- Unknown process names
- Services with strange descriptions
- Processes running as root unnecessarily
- High CPU usage without reason
- Services started recently

---

# 📘 SUMMARY TABLE (FOR NOTES & INTERVIEWS)

## 🧠 PROCESSES & SERVICES

| Command / Concept | Use | Example |
| --- | --- | --- |
| Process | Running program | Browser, malware |
| Service | Background process | SSH |
| `ps` | View terminal processes | `ps` |
| `ps aux` | View all processes | `ps aux` |
| `top` | Real-time monitoring | `top` |
| `htop` | Advanced monitoring | `htop` |
| PID | Process ID | `kill 1234` |
| `systemctl` | Manage services | `systemctl status ssh` |

---

## 🎤 INTERVIEW-READY LINES

Use these confidently:

- **“Every running program in Linux is a process.”**
- **“SOC analysts monitor processes to detect malicious activity.”**
- **“Services are long-running background processes often abused for persistence.”**
- **“Unexpected services or high CPU usage are investigation triggers.”**
