# kali-linux-ethical-hacking-commands
This repository is a structured and practical reference of Kali Linux commands and tools used in ethical hacking and penetration testing. It is designed to help cybersecurity learners, bug bounty hunters, and penetration testers understand what each command does, how it works internally, and where it fits in the real-world hacking methodology.

The repository covers core areas such as information gathering (OSINT), network scanning, enumeration, web application security testing, password auditing, wireless security testing, exploitation frameworks, and post-exploitation analysis using Kali Linux.

All commands are documented with clear explanations and safe example usage, focusing on authorized security testing, learning, and professional penetration testing workflows.

## Kali Linux Ethical Hacking Command Structure

**kali-ethical-hacking-commands/**
* ├── [01-basics](https://github.com/MdJahidShah/kali-linux-ethical-hacking-commands?tab=readme-ov-file#1-system--environment-basics)
* ├── [02-networking](https://github.com/MdJahidShah/kali-linux-ethical-hacking-commands?tab=readme-ov-file#2-network-fundamentals)
* ├── [03-reconnaissance](https://github.com/MdJahidShah/kali-linux-ethical-hacking-commands?tab=readme-ov-file#3-information-gathering-reconnaissance)
* ├── [04-scanning](https://github.com/MdJahidShah/kali-linux-ethical-hacking-commands?tab=readme-ov-file#4-scanning--enumeration)
* ├── [05-web-testing](https://github.com/MdJahidShah/kali-linux-ethical-hacking-commands?tab=readme-ov-file#5-web-application-testing)
* ├── [06-passwords](https://github.com/MdJahidShah/kali-linux-ethical-hacking-commands?tab=readme-ov-file#6-password--authentication-testing)
* ├── [07-wireless](https://github.com/MdJahidShah/kali-linux-ethical-hacking-commands?tab=readme-ov-file#7-wireless-security-authorized-only)
* ├── [08-exploitation](https://github.com/MdJahidShah/kali-linux-ethical-hacking-commands?tab=readme-ov-file#8-exploitation-frameworks)
* ├── [09-post-exploitation](https://github.com/MdJahidShah/kali-linux-ethical-hacking-commands?tab=readme-ov-file#9-post-exploitation-high-level)
* └── [10-reporting](https://github.com/MdJahidShah/kali-linux-ethical-hacking-commands?tab=readme-ov-file#10-reporting--evidence)

Let’s pressure-test the request first.

**Blind spot:** “All estimated commands of Kali Linux” is not a real or useful target. Kali has **thousands** of binaries, and most ethical hackers don’t operate by memorizing commands — they operate by **methodology** (recon → enumeration → exploitation → post-exploitation → reporting).
If you dump everything, your GitHub repo will look noisy and amateur.

**Better strategic move:** Create a **curated, professional command reference**, organized by **ethical hacking phases**, with:

* What the tool/command does
* How it works (high-level, not exploit walkthroughs)
* Example syntax (safe, non-targeted)

Here in the below, there are some most usefull **Kali Linux** Command listed with a few details information. This is the *80/20* set used by real pentesters.

---

## Kali Linux Ethical Hacking Command Reference

---

## 1. System & Environment Basics

> Foundation every hacker must master

| Command | Description            | How it works                  |
| ------- | ---------------------- | ----------------------------- |
| `ls`    | List files/directories | Reads directory inode table   |
| `cd`    | Change directory       | Switches working directory    |
| `pwd`   | Show current path      | Prints absolute path          |
| `cp`    | Copy files             | Duplicates file blocks        |
| `mv`    | Move/rename files      | Updates file references       |
| `rm`    | Delete files           | Removes inode references      |
| `chmod` | Change permissions     | Modifies file permission bits |
| `chown` | Change ownership       | Alters UID/GID mapping        |
| `find`  | Search files           | Traverses filesystem tree     |
| `grep`  | Search text            | Pattern matching via regex    |

---

## 2. Network Fundamentals

> Understanding traffic is non-negotiable

| Command          | Description           | How it works                  |
| ---------------- | --------------------- | ----------------------------- |
| `ip a`           | Show interfaces       | Queries kernel network stack  |
| `ip r`           | Routing table         | Displays packet routing paths |
| `ifconfig`       | Legacy interface tool | Manages NIC configuration     |
| `arp -a`         | ARP table             | Maps IP → MAC                 |
| `netstat -tulnp` | Open ports            | Reads kernel socket table     |
| `ss`             | Socket stats          | Faster netstat replacement    |
| `ping`           | Host reachability     | ICMP echo requests            |
| `traceroute`     | Path discovery        | TTL-based hop mapping         |

---

## 3. Information Gathering (Reconnaissance)

> Ethical hacking starts **before** scanning

| Tool / Command     | Purpose                 | How it works                 |
| ------------------ | ----------------------- | ---------------------------- |
| `whois domain.com` | Domain ownership        | Queries WHOIS DB             |
| `dig domain.com`   | DNS records             | Direct DNS resolution        |
| `nslookup`         | DNS queries             | Resolver-based lookup        |
| `theHarvester`     | OSINT emails/subdomains | Search engine scraping       |
| `amass`            | Asset discovery         | Passive + active enumeration |
| `recon-ng`         | Recon framework         | Modular OSINT automation     |

---

## 4. Scanning & Enumeration

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

## 5. Web Application Testing

> Where most real-world bugs live

| Tool        | Purpose               | How it works                   |
| ----------- | --------------------- | ------------------------------ |
| `whatweb`   | Tech fingerprinting   | HTTP header & content analysis |
| `nikto`     | Web vuln scan         | Signature-based testing        |
| `dirsearch` | Directory brute force | HTTP response analysis         |
| `gobuster`  | Content discovery     | Wordlist-based probing         |
| `wpscan`    | WordPress security    | Plugin/theme CVE checks        |
| `burpsuite` | Web proxy             | Intercepts HTTP requests       |

---

## 6. Password & Authentication Testing

> Controlled credential testing

| Tool      | Description        | How it works           |
| --------- | ------------------ | ---------------------- |
| `hydra`   | Login brute force  | Parallel auth attempts |
| `medusa`  | Password testing   | Threaded login checks  |
| `john`    | Password cracking  | Hash comparison        |
| `hashcat` | GPU cracking       | Optimized hash attacks |
| `crunch`  | Wordlist generator | Pattern-based creation |

---

## 7. Wireless Security (Authorized Only)

> Requires **explicit permission**

| Tool          | Purpose          | How it works       |
| ------------- | ---------------- | ------------------ |
| `iwconfig`    | Wireless setup   | Interface control  |
| `airmon-ng`   | Monitor mode     | Raw packet capture |
| `airodump-ng` | Packet capture   | 802.11 sniffing    |
| `aireplay-ng` | Packet injection | Frame replay       |
| `aircrack-ng` | Key testing      | Handshake analysis |

---

## 8. Exploitation Frameworks

> Proof-of-concept, not destruction

| Tool           | Description           | How it works              |
| -------------- | --------------------- | ------------------------- |
| `msfconsole`   | Metasploit            | Modular exploit framework |
| `searchsploit` | Exploit DB search     | Local exploit database    |
| `sqlmap`       | SQL injection testing | Automated DB probing      |
| `commix`       | Command injection     | Payload automation        |

---

## 9. Post-Exploitation (High-Level)

> Validation, not persistence abuse

| Tool         | Purpose          | How it works         |
| ------------ | ---------------- | -------------------- |
| `linpeas.sh` | Privilege audit  | Misconfig detection  |
| `ps aux`     | Process listing  | Kernel process table |
| `uname -a`   | Kernel info      | OS fingerprint       |
| `sudo -l`    | Permission audit | Allowed commands     |

---

## 10. Reporting & Evidence

> What separates hackers from professionals

| Command       | Purpose          |
| ------------- | ---------------- |
| `script`      | Terminal logging |
| `tee`         | Save output      |
| `markdown`    | Report writing   |
| `screenshots` | Evidence capture |

---

## ⚠️ Disclaimer:  
This repository is intended for educational purposes and authorized security testing only. Do not use these tools or commands on systems you do not own or have explicit permission to test.
