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

### `cat` Command Example

#### Show system users
```bash
┌──(jahid㉿root)-[/]
└─$ cat /etc/passwd
root:x:0:0:root:/root:/bin/bash
...
jahid:x:1000:1000::/home/jahid:/usr/bin/zsh
```
#### Check password hashes (root only)
```bash
┌──(jahid㉿root)-[/]
└─$ sudo cat /etc/shadow
...
jahid:$y$j9T$Zd3O5aADQ4sHFK1IdohLOAVD:20475:0:99999:7:::
```
---

[Return Home](https://mdjahidshah.github.io/kali-linux-ethical-hacking-commands/)