# Linux File System Basics (For Ethical Hackers)

## 🔹 Why this matters
Most sensitive data leaks, misconfigurations, and privilege escalation paths live in the **filesystem**, not tools.

---

## Core File System Commands

| Command     | Description               | How it works                 | Pentester Tip           |
| ----------- | ------------------------- | ---------------------------- | ----------------------- |
| `pwd`       | Show current directory    | Prints absolute working path | Always confirm location |
| `ls`        | List directory contents   | Reads directory entries      | Look for hidden files   |
| `ls -la`    | List all files (detailed) | Shows perms, owner, size     | `.env`, `.git` are gold |
| `cd dir`    | Change directory          | Updates shell working path   | Use absolute paths      |
| `cd ..`     | Go to parent directory    | Moves up directory tree      | Avoid confusion         |
| `tree`      | Directory tree view       | Recursive directory listing  | Quick structure mapping |
| `stat file` | File metadata             | Inode-level info             | Time-based forensics    |

---

## File & Directory Operations

| Command            | Description      | How it works            | Pentester Tip           |
| ------------------ | ---------------- | ----------------------- | ----------------------- |
| `cp file /path/`   | Copy file        | Duplicates file blocks  | Preserve evidence       |
| `cp -r dir /path/` | Copy directory   | Recursive copy          | Backup configs          |
| `mv old new`       | Move / rename    | Updates file references | Rename suspicious files |
| `rm file`          | Delete file      | Removes inode reference | Be careful              |
| `rm -rf dir`       | Force delete     | Recursive unlink        | Dangerous as root       |
| `mkdir dir`        | Create directory | Allocates inode         | Staging payloads        |
| `rmdir dir`        | Remove empty dir | Checks directory state  | Cleanup                 |

---

## Important Linux Directories (Pentester Focus)

| Path        | Purpose             | Why It Matters      |
| ----------- | ------------------- | ------------------- |
| `/etc/`     | Configuration files | Creds, services     |
| `/var/www/` | Web root            | Web shells, configs |
| `/home/`    | User data           | SSH keys, history   |
| `/tmp/`     | Temporary files     | Writable by all     |
| `/opt/`     | Optional apps       | Custom software     |
| `/root/`    | Root user files     | High-value target   |
| `/proc/`    | Process info        | Runtime inspection  |

---

## File Discovery & Analysis

| Command                 | Description        | Pentester Use      |
| ----------------------- | ------------------ | ------------------ |
| `find / -name "*.conf"` | Find config files  | Credential hunting |
| `find / -perm -4000`    | Find SUID binaries | PrivEsc            |
| `du -sh *`              | Directory size     | Spot large dumps   |
| `file filename`         | Detect file type   | Obfuscated files   |
| `strings binary`        | Extract strings    | Malware analysis   |

---

## 🧠 Pro Tips

* **Hidden files matter more than visible ones**
* Always inspect `.env`, `.bak`, `.old`
* Writable directories = exploitation surface

---

[Return Home](https://github.com/MdJahidShah/kali-linux-ethical-hacking-commands?tab=readme-ov-file#kali-linux-ethical-hacking-command-structure)