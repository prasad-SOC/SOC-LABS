# Linux Lab 3 – Log Analysis and Monitoring

## Objective

The goal of this lab is to understand how Linux stores system activity in logs and how to analyze them to identify authentication failures and system errors.

---

## Tools Used

* Linux Terminal
* journalctl command
* Basic Linux commands

---

## Lab Tasks

---

## Task 1 – View Recent Logs

Display the most recent system logs.

```bash
sudo journalctl -n 50
```

---

## Task 2 – Identify Failed Login Attempts

Search logs for failed authentication attempts.

```bash
sudo journalctl | grep -i "failed"
```

---

## Task 3 – Check System Errors

Filter logs to display only error-level messages.

```bash
sudo journalctl -p err
```

---

## Task 4 – Count Failed Attempts

Count how many failed login attempts occurred.

```bash
sudo journalctl | grep -i "failed" | wc -l
```

---

## Task 5 – Identify Repeated Patterns

Check for repeated failed login attempts.

```bash
sudo journalctl | grep -i "failed" | sort | uniq -c
```

---

## Task 6 – Filter Recent Suspicious Activity

View recent logs and filter for errors and failures.

```bash
sudo journalctl --since "1 hour ago" | grep -Ei "failed|error"
```

---

## Key Concepts Learned

* System logging in Linux
* Using journalctl for log analysis
* Identifying failed authentication attempts
* Filtering logs using grep
* Detecting repeated suspicious patterns

---

## Security Insight

Logs provide visibility into system activity.

Repeated failed login attempts may indicate **brute-force attacks**, while frequent errors can point to **system issues or misconfigurations**.

Regular log monitoring is essential for detecting suspicious behavior and supporting SOC operations.

---
