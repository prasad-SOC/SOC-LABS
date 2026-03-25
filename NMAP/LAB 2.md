# 🔍 Nmap Lab 2 — Port Scanning & Nmap Scripting Engine (NSE)

## 🎯 Objective

In this lab, we will go deeper into Nmap by focusing on two important areas:

* Understanding different types of port scanning techniques
* Using the Nmap Scripting Engine (NSE) to extract more detailed information from a target

By the end of this lab, you should be comfortable identifying open ports and using scripts to gather useful intelligence.

---

## 🛠️ Prerequisites

Before starting, ensure you have the following:

* Kali Linux or any Linux distribution with Nmap installed
* Basic understanding of networking concepts
* A safe target environment

### 🎯 Target IPs (Use one of these)

* Local Lab Machine: `192.168.1.10`
* Official Test Server: `scanme.nmap.org`

⚠️ Important: Only scan systems you have permission to test.

---

# 📌 Task 1 — Basic Port Scan

### Command:

```bash
nmap 192.168.1.10
```

### Explanation:

This is the default scan performed by Nmap. It scans the top 1000 most commonly used ports on the target system.

### What to Observe:

* List of open ports
* Services running on those ports
* Port states such as open, closed, or filtered

---

# 📌 Task 2 — Scan Specific Ports

### Command:

```bash
nmap -p 22,80,443 192.168.1.10
```

### Explanation:

This command scans only selected ports instead of scanning all common ports. It is useful when you want to focus on specific services.

### What to Observe:

* Whether the selected ports are open or closed
* Which services are active on those ports

---

# 📌 Task 3 — Scan a Range of Ports

### Command:

```bash
nmap -p 1-1000 192.168.1.10
```

### Explanation:

This scans a continuous range of ports. It provides more coverage than the default scan and may reveal additional services.

### What to Observe:

* Additional open ports not found in default scan
* Differences compared to Task 1

---

# 📌 Task 4 — Scan All Ports

### Command:

```bash
nmap -p- 192.168.1.10
```

### Explanation:

This command scans all 65535 ports on the target system. It is the most thorough scan but takes more time.

### What to Observe:

* Any uncommon or hidden services
* Time taken compared to other scans

---

# 📌 Task 5 — Fast Scan

### Command:

```bash
nmap -F 192.168.1.10
```

### Explanation:

This performs a faster scan by scanning fewer ports than the default scan.

### What to Observe:

* Reduced scan time
* Possible missing ports compared to full scans

---

# 📌 Task 6 — TCP SYN Scan (Stealth Scan)

### Command:

```bash
sudo nmap -sS 192.168.1.10
```

### Explanation:

This is known as a stealth scan because it does not complete the full TCP handshake. It is faster and less likely to be logged.

### What to Observe:

* Similar results to basic scan
* Faster execution

---

# 📌 Task 7 — UDP Scan

### Command:

```bash
sudo nmap -sU 192.168.1.10
```

### Explanation:

UDP scans check for services running on UDP ports such as DNS or SNMP. These scans are slower and sometimes less reliable.

### What to Observe:

* Open or filtered UDP ports
* Differences compared to TCP scan results

---

# 🔍 Nmap Scripting Engine (NSE)

## 📌 Task 8 — Default Scripts

### Command:

```bash
nmap -sC 192.168.1.10
```

### Explanation:

This runs a set of default scripts that are safe and useful for basic enumeration.

### What to Observe:

* Additional information about services
* Script outputs providing extra details

---

## 📌 Task 9 — Run a Specific Script

### Command:

```bash
nmap --script=http-title 192.168.1.10
```

### Explanation:

This script retrieves the title of a web page hosted on the target.

### What to Observe:

* Web application title
* Any useful identifying information

---

## 📌 Task 10 — Run Multiple Scripts

### Command:

```bash
nmap --script=http-* 192.168.1.10
```

### Explanation:

This runs all scripts related to HTTP services.

### What to Observe:

* Detailed HTTP information
* Server configuration insights

---

## 📌 Task 11 — Vulnerability Scan

### Command:

```bash
nmap --script=vuln 192.168.1.10
```

### Explanation:

This attempts to detect known vulnerabilities using available NSE scripts.

### What to Observe:

* Reported vulnerabilities
* False positives (not always accurate)

---

## 📌 Task 12 — Service Version + Scripts

### Command:

```bash
nmap -sV --script=default 192.168.1.10
```

### Explanation:

This combines service version detection with default scripts to provide deeper insights.

### What to Observe:

* Service versions
* Additional script-based information

---

# 📊 Final Observations

After completing all tasks, you should be able to:

* Identify open ports and running services
* Understand differences between scan types
* Use NSE for deeper enumeration

---

# 🧠 Lab Summary

Port scanning helps identify potential entry points in a system, while NSE enhances scanning by providing detailed information and possible vulnerabilities. Together, they form a critical part of reconnaissance in cybersecurity.

---

# 📌 Notes

* Always perform scans in a legal and authorized environment
* Full scans can take significant time
* NSE vulnerability results should always be verified manually
