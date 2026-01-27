# ⚡ RIPGREP (`rg`) — MODERN GREP ALTERNATIVE

## What is ripgrep?

`ripgrep` (`rg`) is a **modern, faster replacement for grep**, written in Rust.
It is optimized for **large codebases**, respects `.gitignore`, and searches recursively by default.

---

## Why Pentesters Prefer `rg`

| Feature               | grep   | rg        |
| --------------------- | ------ | --------- |
| Recursive by default  | ❌      | ✅         |
| Speed                 | Medium | Very Fast |
| Respects `.gitignore` | ❌      | ✅         |
| Cleaner output        | ❌      | ✅         |
| Binary detection      | Manual | Automatic |

---

## Example Comparison

### grep

```bash
grep -R "password" .
```

### ripgrep

```bash
rg "password"
```

Same result. Less typing. Faster.

---

## Pentester Use Cases for `rg`

| Scenario          | Command              |        |       |
| ----------------- | -------------------- | ------ | ----- |
| Search secrets    | `rg "password        | secret | key"` |
| Web shell hunting | `rg "base64_decode"` |        |       |
| API keys          | `rg "AKIA"`          |        |       |
| Config review     | `rg "DB_"`           |        |       |

---

## When NOT to Use `rg`

* Minimal systems (not installed)
* Binary-heavy environments
* Legacy scripts expecting grep exit codes

---

# 🧠 A LINUX‑FOR‑PENTESTERS MINI HANDBOOK

*(Create `linux-for-pentesters.md` in root or `01-linux-basics/`)*

## Core Philosophy

> Tools don’t find vulnerabilities.
> **Understanding the system does.**

---

## Essential Mental Models

### 1️⃣ Everything is a File

* Processes
* Devices
* Sockets
* Logs

### 2️⃣ Permissions Control Power

* Files
* Processes
* Privilege escalation

### 3️⃣ PATH Is an Attack Surface

```bash
echo $PATH
```

---

## Must-Know Command Categories

| Category    | Commands                    |
| ----------- | --------------------------- |
| Navigation  | `ls`, `cd`, `pwd`           |
| Discovery   | `find`, `locate`, `grep`    |
| Permissions | `chmod`, `chown`, `sudo -l` |
| Processes   | `ps`, `top`, `htop`         |
| Networking  | `ss`, `ip`, `netstat`       |
| Logs        | `journalctl`, `cat`, `less` |

---

## High-Value Files Every Pentester Checks

| File                   | Why         |
| ---------------------- | ----------- |
| `/etc/passwd`          | Users       |
| `/etc/shadow`          | Hashes      |
| `.bash_history`        | Commands    |
| `.ssh/authorized_keys` | Persistence |
| `.env`                 | Secrets     |
| `config.php`           | DB creds    |

---

## Golden Rules (Real-World)

* Never run destructive commands blindly
* Always check permissions before exploits
* Read configs before scanning
* Filter output, don’t drown in it
* Document everything

---

[Return Home](https://github.com/MdJahidShah/kali-linux-ethical-hacking-commands?tab=readme-ov-file#kali-linux-ethical-hacking-command-structure)