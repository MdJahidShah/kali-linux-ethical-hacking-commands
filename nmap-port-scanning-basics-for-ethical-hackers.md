# Nmap Port Scanning Basics (For Ethical Hackers)

## 🔹 Why Nmap Matters
Nmap (Network Mapper) is the **first weapon** in any ethical hacker’s workflow.  
Before exploitation, you must know **what is alive, what is open, and what is vulnerable**.

No ports → no services → no attack surface.

---

## Understanding IP Addresses

### Types of IP Addresses

| Type | Description | Pentester Relevance |
|----|------------|---------------------|
| Public IP | Routable on the internet | External attack surface |
| Private IP | Internal networks (192.168.x.x, 10.x.x.x) | Internal pentesting |
| Static IP | Fixed address | Easier recon |
| Dynamic IP | Changes over time | Harder to track |

---

## Understanding Ports (Critical Concept)

A **port** is a logical communication endpoint used by services.

**Port Range:** `0 – 65535`

| Range | Type | Examples |
|-----|-----|----------|
| 0–1023 | Well‑Known Ports | HTTP (80), HTTPS (443), SSH (22) |
| 1024–49151 | Registered | App‑specific |
| 49152–65535 | Dynamic / Ephemeral | Client connections |

### 🧠 Pentester Analogy (Corrected)
- **IP Address** → Building  
- **Port** → Room  
- **Service** → What’s running inside the room  

> ⚠️ Note:  
> MAC addresses do **not** contain ports.  
> Ports belong to **IP + Protocol**, not MAC addresses.

---

## Common Protocols & Ports

| Protocol | Port | Purpose |
|--------|------|--------|
| HTTP | 80 | Web traffic |
| HTTPS | 443 | Secure web |
| FTP | 21 | File transfer |
| SSH | 22 | Remote shell |
| DNS | 53 | Domain resolution |
| SMTP | 25 | Email sending |

---

## What Nmap Actually Does

Nmap scans **ports**, identifies **services**, detects **versions**, and maps **attack surfaces**.

Pentesters use Nmap to:
- Discover open ports
- Identify running services
- Detect software versions
- Find misconfigurations
- Run vulnerability scripts

---

## Basic Port Scanning

### Scan Specific Ports
```bash
nmap -p 22,21 192.168.0.1
```

**What it does:**
Checks if SSH (22) and FTP (21) are open.

**Pentester Tip:**
Target known high‑risk ports first.

---

## Full Port Scan

```bash
nmap -p 1-65535 IP_ADDRESS
```

**Why this matters:**
Default Nmap scans only **1000 ports** — critical services may be missed.

---

## Stealth Scan (SYN Scan)

```bash
nmap -sS IP_ADDRESS
```

**How it works:**
Sends SYN packets without completing TCP handshake.

**Pentester Tip:**

* Faster
* Less noisy
* Requires root

---

## Service & Version Detection

```bash
nmap -sV IP_ADDRESS
```

**What it reveals:**

* Apache vs Nginx
* OpenSSH version
* FTP software

**Why this is gold:**
Exploit databases are **version‑specific**.

---

## Combined Scan (Professional Standard)

```bash
nmap -sS -sV IP_ADDRESS
```

This is the **minimum serious scan** for real engagements.

---

## Vulnerability Detection with Nmap Scripts

```bash
nmap --script vuln IP_ADDRESS
```

**What it does:**
Runs NSE scripts to detect:

* Known CVEs
* Misconfigurations
* Weak services

**Pentester Tip:**
This does **not replace manual testing** — it only points directions.

---

## Website Misconfiguration Scanning (Real Workflow)

### Step 1: Identify Open Ports

```bash
nmap WEBSITE_IP
```

---

### Step 2: Detect Services & Versions

```bash
nmap -sS -sV WEBSITE_IP
```

Focus on:

* Web server version
* SSL services
* Admin panels

---

### Step 3: Full Deep Scan

```bash
nmap -p 1-65535 -sS -sV WEBSITE_IP
```

**Use when:**

* Bug bounty
* Internal pentest
* High‑value target

---

## 🧠 Real Pentester Notes

* Open ports ≠ vulnerability (context matters)
* Old versions ≠ exploitable (check mitigations)
* Always verify manually
* Combine Nmap with:

  * `searchsploit`
  * `nikto`
  * `gobuster`

---

## ⚠️ Legal Warning

Only scan systems you **own** or have **explicit permission** to test.

Unauthorized scanning is illegal.

---

[⬅ Return Home](https://mdjahidshah.github.io/kali-linux-ethical-hacking-commands/)