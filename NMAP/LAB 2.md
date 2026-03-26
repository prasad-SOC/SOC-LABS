# 🔍 Nmap Lab 2 — Port Scanning & NSE (Using scanme.nmap.org)

## 🎯 Objective

This lab focuses on performing meaningful Nmap scans using a real and responsive target. The goal is to:

* Identify open ports
* Detect running services
* Use NSE scripts to gather additional information

---

## 🛠️ Prerequisites

* Kali Linux / Linux system
* Nmap installed
* Internet connection

### 🎯 Target Used

```
scanme.nmap.org
```

⚠️ Note: This is an official test server provided for learning purposes. Some scans may be limited or filtered.

---

# 📌 Task 1 — Basic Scan

```bash
nmap scanme.nmap.org
```

### Explanation:

Performs a default scan on the top 1000 ports.

### Observation:

* Identify open ports (commonly 22, 80)
* Note port states (open/filtered)

---

# 📌 Task 2 — Service Version Detection

```bash
nmap -sV scanme.nmap.org
```

### Explanation:

Detects service versions running on open ports.

### Observation:

* Service names and versions
* Additional details about services

---

# 📌 Task 3 — SYN Scan (Stealth)

```bash
sudo nmap -sS scanme.nmap.org
```

### Explanation:

Performs a stealth scan without completing full TCP handshake.

### Observation:

* Compare results with basic scan
* Note speed and behavior differences

---

# 📌 Task 4 — Specific Ports Scan

```bash
nmap -p 22,80,443 scanme.nmap.org
```

### Explanation:

Scans only selected ports.

### Observation:

* Confirm which ports are open
* Identify services on those ports

---

# 📌 Task 5 — NSE Default Scripts

```bash
nmap -sC scanme.nmap.org
```

### Explanation:

Runs default safe scripts for enumeration.

### Observation:

* Additional service details
* Script outputs

---

# 📌 Task 6 — NSE HTTP Script

```bash
nmap --script=http-title scanme.nmap.org
```

### Explanation:

Retrieves the title of the web page.

### Observation:

* Web application title
* Useful identifying information

---

# 📊 Final Observations

* Open ports indicate active services
* Service detection provides deeper insights
* NSE enhances scanning with additional information
* Results may vary due to server restrictions

---

# 🧠 Conclusion

This lab demonstrates how to perform practical port scanning and basic enumeration using a real-world test server. It highlights the importance of choosing the right target for meaningful results.

---

# ⚠️ Notes

* Avoid aggressive scans on public targets
* Results may be limited due to security controls
* Always scan authorized systems only
