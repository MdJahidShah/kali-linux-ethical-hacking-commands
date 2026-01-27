# 🔁 FIND vs GREP — DEEP COMPARISON

*(Create a section in `grep-command.md` or a separate `find-vs-grep.md`)*

## Conceptual Difference (First Principles)

| Tool   | Primary Purpose                |
| ------ | ------------------------------ |
| `find` | Locate files based on metadata |
| `grep` | Search content inside files    |

> **find answers “WHERE”**
> **grep answers “WHAT”**

---

## Functional Comparison Table

| Feature                | `find`  | `grep`          |
| ---------------------- | ------- | --------------- |
| Searches file names    | ✅       | ❌               |
| Searches file content  | ❌       | ✅               |
| Uses regex             | Limited | Full regex      |
| Filters by permissions | ✅       | ❌               |
| Filters by size/time   | ✅       | ❌               |
| Recursive by default   | ❌       | ❌ (`-R` needed) |
| Used for priv esc      | ✅       | ⚠️              |
| Used for secrets       | ⚠️      | ✅               |

---

## Real Pentester Usage (Combined Power)

### Find files → Grep content

```bash
find /var/www -name "*.php" | xargs grep "password"
```

### Find SUID binaries

```bash
find / -perm -4000 2>/dev/null
```

### Grep inside discovered files

```bash
grep -R "root" /etc/
```

> **Elite workflow:** `find` narrows the target → `grep` extracts the signal.

---