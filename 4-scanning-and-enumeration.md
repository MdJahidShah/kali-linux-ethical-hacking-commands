# 4. Scanning & Enumeration

> Identifying attack surface

| Tool         | Description       | How it works                    |
| ------------ | ----------------- | ------------------------------- |
| `nmap`       | Network scanner   | TCP/IP probing + fingerprinting |
| `nmap -sV`   | Service detection | Banner & protocol analysis      |
| `nmap -O`    | OS detection      | TCP/IP stack fingerprint        |
| `masscan`    | Fast port scan    | Asynchronous SYN scanning       |
| `enum4linux` | SMB enumeration   | Null session probing            |
| `snmpwalk`   | SNMP enumeration  | OID tree traversal              |

---

[Return Home](https://github.com/MdJahidShah/kali-linux-ethical-hacking-commands?tab=readme-ov-file#kali-linux-ethical-hacking-command-structure)