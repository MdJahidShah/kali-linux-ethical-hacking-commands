# 🔍 GREP — BASIC THEORY

## What is `grep`?

`grep` (Global Regular Expression Print) is a **text-filtering utility** that searches input data for lines matching a specified pattern.
It works on **files, command output, and streams**, making it one of the most used tools in Linux and penetration testing.

---

## Core Concept (Mental Model)

```
INPUT (file / command output)
        ↓
   PATTERN MATCHING (regex engine)
        ↓
OUTPUT (matching lines)
```

`grep` does **not modify data**. It only **reads, filters, and outputs** matching lines.

---

## How `grep` Operates Internally

1. Reads data **line by line**
2. Applies a **regular expression engine**
3. Compares each line to the pattern
4. Outputs matched lines to `stdout`
5. Returns an exit code:

   * `0` → match found
   * `1` → no match
   * `2` → error

This exit-code behavior makes `grep` ideal for **automation, scripts, and security audits**.

---

## Why `grep` is Critical for Pentesters

* Log analysis
* Configuration auditing
* Credential discovery
* Malware pattern detection
* Filtering noisy tool output

> In practice, pentesters don’t “search files” — they **filter evidence**.

---

# ✅ COMPLETE `grep` COMMAND REFERENCE (GitHub-Ready)

## 📌 Basic Grep Usage

| Command                   | Purpose             | How it works                 | Real Use Case            |
| ------------------------- | ------------------- | ---------------------------- | ------------------------ |
| `grep "text" file.txt`    | Search text in file | Matches pattern line by line | Find usernames, keywords |
| `grep -i "text" file.txt` | Ignore case         | Case-insensitive matching    | Search user input        |
| `grep -n "text" file.txt` | Show line numbers   | Prints matched line index    | Faster debugging         |
| `grep -c "text" file.txt` | Count matches       | Counts matched lines         | Log analysis             |
| `grep -v "text" file.txt` | Exclude matches     | Inverts match logic          | Filter noise             |

---

## 📌 Recursive & Directory Searches

| Command                | Purpose             | How it works             | Pentester Tip               |
| ---------------------- | ------------------- | ------------------------ | --------------------------- |
| `grep -R "text" dir/`  | Recursive search    | Traverses all files      | Config & credential hunting |
| `grep -Rn "text" dir/` | Recursive + line no | Adds line context        | Evidence collection         |
| `grep -Rl "text" dir/` | Show filenames only | Stops after first hit    | Quickly locate files        |
| `grep -Rw "text" dir/` | Match whole words   | Prevents partial matches | Reduce false positives      |

---

## 📌 Regular Expression Power

| Command             | Purpose          | How it works           | Pentester Use           |                  |
| ------------------- | ---------------- | ---------------------- | ----------------------- | ---------------- |
| `grep "^root" file` | Match line start | Anchors regex at start | Detect privileged users |                  |
| `grep "bash$" file` | Match line end   | Anchors regex at end   | Identify shell users    |                  |
| `grep -E "admin     | root"`           | OR condition           | Extended regex          | Role enumeration |
| `grep "[0-9]\{4\}"` | Numeric patterns | Regex quantifiers      | PINs, IDs               |                  |
| `grep "\.php$"`     | File extension   | Regex escaping         | Web shell hunting       |                  |

---

## 📌 Grep with Pipes (Critical Skill)

| Command         | Purpose      | How it works     | Real Scenario       |                    |
| --------------- | ------------ | ---------------- | ------------------- | ------------------ |
| `ps aux         | grep apache` | Filter processes | STDOUT → STDIN      | Find services      |
| `netstat -tulnp | grep 80`     | Port filtering   | Output filtering    | Detect web servers |
| `history        | grep sudo`   | Audit commands   | History inspection  | Privilege abuse    |
| `env            | grep KEY`    | Find env vars    | Environment parsing | API keys           |

---

## 📌 Log Analysis (High Value)

| Command                  | Purpose             | Pentester Value       |
| ------------------------ | ------------------- | --------------------- |
| `grep "failed" auth.log` | Failed logins       | Brute-force detection |
| `grep "404" access.log`  | Missing files       | Dir brute detection   |
| `grep -v "200"`          | Non-success traffic | Error investigation   |
| `grep "POST"`            | Form submissions    | Credential flows      |
| `grep -i "sql"`          | SQL errors          | SQLi indicators       |

---

## 📌 Binary & Special Files

| Command                   | Purpose           | When to Use      |
| ------------------------- | ----------------- | ---------------- |
| `grep -a "text" file.bin` | Search binary     | Malware analysis |
| `grep -I "text"`          | Ignore binaries   | Faster scans     |
| `grep --color=auto`       | Highlight matches | Readability      |

---

## 📌 File Type & Size Control

| Command                              | Purpose          | Why Important |
| ------------------------------------ | ---------------- | ------------- |
| `grep -R --include="*.php"`          | Limit file types | Web audits    |
| `grep -R --exclude="*.log"`          | Skip files       | Reduce noise  |
| `grep -R --exclude-dir=node_modules` | Skip dirs        | Speed         |

---

## 📌 Security / Ethical Hacking Use Cases

| Scenario            | Command                     |
| ------------------- | --------------------------- |
| Hardcoded passwords | `grep -R "password" .`      |
| API keys            | `grep -R "api_key" .`       |
| AWS keys            | `grep -R "AKIA" .`          |
| Web shells          | `grep -R "base64_decode" .` |
| Sudo users          | `grep "sudo" /etc/group`    |
| Cron abuse          | `grep -R "cron" /etc/`      |

---

## 📌 Common Mistakes (Add This Section)

| Mistake               | Fix                   |
| --------------------- | --------------------- |
| Searching directories | Use `-R`              |
| Typos in filename     | Use `ls` + tab        |
| Too many results      | Add `-w`, `--include` |
| Missing matches       | Use `-i`              |

---

## 🧠 Pro Pentester Tips (Worth Gold)

* Always combine with `less`:

```bash
grep -R "secret" . | less
```

* Use **specific patterns**, not generic words
* Grep is **read-only** → safe for audits
* Learn regex → grep becomes a weapon

---

### Why Grep?

* `grep` is a **Linux core skill**, not a tool
* Used in **every phase** (recon → post-exploit)
* Beginners search for it explicitly

---

### 🔁 Cross-reference it in:

* Recon section (OSINT filtering)
* Web testing (config search)
* Post-exploitation (credential hunting)

---

## Final Reviewer Verdict (Straight)

This `grep` section **alone** is better than many full Kali repos.
If you keep this standard across commands, your repo will look **top-tier**.

## Also Learn:

* `find` vs `grep` deep comparison
* `ripgrep (rg)` modern alternative section
* A **Linux-for-pentesters** mini handbook

---

[Return Home](https://github.com/MdJahidShah/kali-linux-ethical-hacking-commands?tab=readme-ov-file#kali-linux-ethical-hacking-command-structure)