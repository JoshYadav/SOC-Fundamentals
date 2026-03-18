#  NANO & VIM EDITOR

Where analysts use editors:

### 1️⃣ Viewing log files

Example:

```bash
nano /var/log/auth.log
```

Faster than scrolling with cat.

---

### 2️⃣ Editing configuration during incident

Example:

- Disable a service
- Change a setting
- Add monitoring rule

---

### 3️⃣ Writing investigation notes on server

Example:

- Save timeline
- Document findings

---

# 🟦 vim vs nano (IMPORTANT)

| Editor | Difficulty | Usage in SOC |
| --- | --- | --- |
| nano | Easy | Most common for beginners |
| vim | Harder | Used in enterprise environments |

SOC L1 expectation:

👉 Be comfortable with **nano**

👉 Know basic vim navigation

Nothing beyond that.

---

# 🟦 BASIC NANO COMMANDS (YOU MUST KNOW)

Open file:

```bash
nano filename
```

Inside nano:

| Action | Shortcut |
| --- | --- |
| Save | Ctrl + O |
| Exit | Ctrl + X |
| Search | Ctrl + W |
| Cut line | Ctrl + K |
| Paste | Ctrl + U |

That’s all you need.

---

# 🟦 BASIC VIM COMMANDS (ONLY ESSENTIAL)

Open file:

```bash
vim filename
```

Modes:

### Normal mode

Default mode for navigation.

### Insert mode

Press:

```bash
i
```

to start typing.

### Save & exit:

Press:

```bash
ESC
:wq
```

### Exit without saving:

```bash
ESC
:q!
```

These 4 commands are enough.

---

# 📘 SUMMARY TABLE (FINAL ADDITION)

| Command | Use |
| --- | --- |
| `nano file` | Easy editing |
| `Ctrl+O` | Save in nano |
| `Ctrl+X` | Exit nano |
| `vim file` | Advanced editor |
| `i` | Insert mode |
| `:wq` | Save & exit vim |
| `:q!` | Exit without saving |

---

# 🎤 INTERVIEW-READY LINE

You can say:

> “I use nano for quick file editing and basic vim commands for navigating and modifying configuration or log files during investigations.”
>
