# 🔐 Permissions

## Linux File Permissions & Ownership (Security-Critical)

### 🔹 Why this matters

**Misconfigured permissions are one of the top Linux privilege escalation vectors.**

---

## Permission Basics

| Permission | Symbol | Meaning            |
| ---------- | ------ | ------------------ |
| Read       | `r`    | View file contents |
| Write      | `w`    | Modify file        |
| Execute    | `x`    | Run file           |

Permission format:

```
-rwxr-xr--
```

---

## Permission Structure

| Section   | Meaning            |
| --------- | ------------------ |
| First `-` | File type          |
| `rwx`     | Owner permissions  |
| `r-x`     | Group permissions  |
| `r--`     | Others permissions |

---

## Permission Commands

| Command            | Description      | How it works            | Pentester Tip           |
| ------------------ | ---------------- | ----------------------- | ----------------------- |
| `chmod 755 file`   | Set permissions  | Numeric permission bits | Web roots often mis-set |
| `chmod +x file`    | Make executable  | Adds execute bit        | Payload prep            |
| `chown user file`  | Change owner     | Updates UID             | Ownership abuse         |
| `chgrp group file` | Change group     | Updates GID             | Group escalation        |
| `ls -l`            | View permissions | Reads inode metadata    | First audit step        |
| `chmod 777 file`   | Change permissions| Modifies access bits  | Dangerous in prod       |
| `id`               | User info        | Shows UID/GID           | Detect privileges       |
---

## Numeric Permission Meaning

| Number | Permission |
| ------ | ---------- |
| `7`    | rwx        |
| `6`    | rw-        |
| `5`    | r-x        |
| `4`    | r--        |
| `0`    | ---        |

Example:

```bash
chmod 640 file
```

Owner: rw-, Group: r--, Others: ---

---

## Special Permissions (Critical)

| Permission | Symbol | Purpose         | Pentester Use |
| ---------- | ------ | --------------- | ------------- |
| SUID       | `s`    | Run as owner    | PrivEsc       |
| SGID       | `s`    | Run as group    | Shared access |
| Sticky bit | `t`    | Restrict delete | `/tmp` abuse  |

### Find SUID files

```bash
find / -perm -4000 2>/dev/null
```

---

## Dangerous Permission Patterns

| Pattern                 | Risk              |
| ----------------------- | ----------------- |
| `777`                   | World-writable    |
| Writable `/etc`         | System takeover   |
| Writable cron files     | Persistent access |
| Root-owned but writable | PrivEsc           |

---

## 🧠 Pro Pentester Tips

* Always audit permissions **before exploits**
* SUID + writable binary = instant red flag
* Check cron jobs + permissions together

---

[Return Home](https://mdjahidshah.github.io/kali-linux-ethical-hacking-commands/)