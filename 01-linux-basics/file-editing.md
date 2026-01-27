# File Viewing & Editing (Pentester Usage)

## Why this matters
Credentials, tokens, API keys, and configs are stored in plain text.

---

| Command | Description | How it works | Pentester Tip |
|-------|------------|-------------|--------------|
| `cat file` | View file | Dumps file to stdout | Fast inspection |
| `less file` | Paginated view | Loads file incrementally | Safe for large files |
| `nano file` | Edit file | Terminal text editor | Beginner friendly |
| `vim file` | Edit file | Modal editor | Power users |
| `tail -f log` | Live log view | Streams appended data | Monitor attacks |

---

[Return Home](https://github.com/MdJahidShah/kali-linux-ethical-hacking-commands?tab=readme-ov-file#kali-linux-ethical-hacking-command-structure)