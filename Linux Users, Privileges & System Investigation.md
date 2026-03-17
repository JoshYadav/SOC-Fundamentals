## Lesson 8: Users, Privileges & System Investigation

This is the last critical Linux block before we close Phase 1.

---

# 1️⃣ Who Is Logged In?

Run:

```bash
who
```

Shows:

- Active logged-in users

SOC relevance:

- Detect unexpected sessions

---

Run:

```bash
w
```

Shows:

- Who is logged in
- What they are doing

SOC relevance:

- Detect suspicious activity
- See active commands

---

# 2️⃣ User Account Investigation

Run:

```bash
cat /etc/passwd
```

This lists:

- All users on system

SOC relevance:

- Detect unauthorized accounts
- Identify system vs normal users

---

Run:

```bash
sudocat /etc/shadow
```

(You’ll need sudo)

SOC relevance:

- Check password hash storage
- Confirm account security

You don’t need to understand hash formats deeply yet.

---

# 3️⃣ Group Investigation

Run:

```bash
cat /etc/group
```

SOC relevance:

- Check who belongs to sudo group
- Detect privilege escalation attempts

---

# 4️⃣ Sudo Activity Logs

Run:

```bash
grepsudo /var/log/auth.log
```

SOC relevance:

- Detect unexpected privilege use
- See escalation attempts

---

# 5️⃣ Check Listening Ports Again (With Context)

Run:

```bash
ss -tulpn
```

Now ask yourself:

- Which services are listening?
- Should they be running?

This is investigation mindset training.

---

# 6️⃣ Check Scheduled Tasks (Persistence Check)

Run:

```bash
crontab -l
```

SOC relevance:

- Malware persistence via cron jobs

If it says no crontab, that’s normal.

---

# 📘 SUMMARY TABLE

| Command | Use | Example |
| --- | --- | --- |
| `who` | Logged-in users | `who` |
| `w` | Active user sessions | `w` |
| `/etc/passwd` | List users | `cat /etc/passwd` |
| `/etc/group` | List groups | `cat /etc/group` |
| `grep sudo` | Check sudo logs | `grep sudo auth.log` |
| `crontab -l` | Check scheduled tasks | `crontab -l` |

---

# 🎤 Interview-Ready Lines

You can now say:

- “I check `/etc/passwd` and `/etc/group` to detect unauthorized accounts.”
- “Sudo logs help identify privilege escalation.”
- “Cron jobs are common persistence mechanisms.”
- “User session monitoring helps detect unauthorized access.”
