## Nmap Lab 1 — Basic & Important Scans

---

## 🎯 Objective

**Fact:**
Practice the most essential scanning techniques using Nmap to:

* Identify active hosts
* Discover open ports
* Detect services and operating systems

---

## ⚠️ Safety Note

**Fact:**
Only scan systems you **own** or have **permission** to test.

---

# 🧪 Tasks & Commands

---

## 🔹 Task 1 — Basic Scan

```bash
nmap <target-ip>
```

### Explanation:

* Scans top 1000 common ports
* Shows open, closed, filtered ports

---

## 🔹 Task 2 — Specific Host Scan

```bash
nmap 192.168.1.10
```

### Explanation:

* Scans a single target system
* Same as basic scan but explicit target

---

## 🔹 Task 3 — Multiple Hosts Scan

```bash
nmap 192.168.1.10 192.168.1.20
```

### Explanation:

* Scans multiple targets at once
* Saves time in multi-host environments

---

## 🔹 Task 4 — Network Range Scan

```bash
nmap 192.168.1.0/24
```

### Explanation:

* Scans an entire subnet
* Useful for discovering multiple systems

---

## 🔹 Task 5 — Ping Scan (Host Discovery)

```bash
nmap -sn 192.168.1.0/24
```

### Explanation:

* Identifies live hosts only
* Does NOT scan ports

---

## 🔹 Task 6 — Service & Version Detection

```bash
nmap -sV <target-ip>
```

### Explanation:

* Detects running services
* Shows versions (e.g., Apache, SSH)

---

## 🔹 Task 7 — OS Detection

```bash
nmap -O <target-ip>
```

### Explanation:

* Attempts to identify operating system

**Data note:**
Accuracy is not guaranteed → depends on network conditions

---

## 🔹 Task 8 — Aggressive Scan

```bash
nmap -A <target-ip>
```

### Explanation:

* Combines multiple scans:

  * OS detection
  * Version detection
  * Script scanning
  * Traceroute

---
