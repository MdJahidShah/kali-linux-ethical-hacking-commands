# Package Management (Kali Linux)

## Why this matters
Outdated tools = failed exploits.

---

| Command | Description | How it works | Pentester Tip |
|-------|------------|-------------|--------------|
| `sudo apt update` | Refresh package list | Syncs repo metadata | Run daily |
| `sudo apt upgrade` | Upgrade packages | Updates installed tools | Avoid breaking exploits |
| `sudo apt full-upgrade` | Full system upgrade | Handles deps + kernel | Use cautiously |
| `apt search tool` | Search packages | Queries repo index | Find alternatives |
| `apt show tool` | Package details | Displays metadata | Read before install |
| `sudo apt install tool` | Install package | Downloads + installs | Prefer official repos |
| `sudo apt remove tool` | Remove package | Deletes binaries | Clean system |

---

[Return Home](https://mdjahidshah.github.io/kali-linux-ethical-hacking-commands/)