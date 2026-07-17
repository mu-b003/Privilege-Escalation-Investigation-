# Privilege Escalation Investigation

## Overview

This project documents a practical Linux privilege escalation investigation performed in an isolated virtual lab environment.

The objective was to simulate an attacker attempting to gain elevated privileges on a Linux server, then investigate the generated authentication logs to determine whether the attack succeeded.

---

## Objectives

- Simulate attacker activity through SSH.
- Attempt multiple privilege escalation techniques.
- Analyze Linux authentication logs.
- Identify failed privilege escalation attempts.
- Produce evidence-based findings.

---

## Lab Environment

| Component | Details |
|----------|---------|
| Operating System | Ubuntu Server |
| Attacker Machine | Kali Linux |
| Log File | /var/log/auth.log |
| Protocol | SSH |
| Analysis Tools | grep, awk, sort, last |

---

## Investigation Summary

The attacker successfully authenticated using the **Afreen** account over SSH.

After login, several privilege escalation attempts were performed, including:

- Checking sudo permissions
- Attempting to switch to root using `su`
- Reading `/etc/shadow`
- Accessing `/root`
- Searching for SUID binaries

Log analysis confirmed that every privilege escalation attempt failed.

No evidence was found indicating that root privileges were obtained.

---

## Key Findings

- Successful SSH login
- Multiple privilege escalation attempts
- sudo access denied
- Failed `su` authentication
- Access denied to sensitive files
- No root login detected
- Single attacker IP identified

---

## Indicators of Compromise (IOCs)

- Source IP: 192.168.81.128
- Target User: Afreen
- Service: SSH
- Failed sudo attempts
- Failed su authentication

---

## Repository Structure

```
commands/
docs/
evidence/
logs/
reports/
README.md
LICENSE
DISCLAIMER.md
```

---

## Skills Demonstrated

- Linux Log Analysis
- Authentication Investigation
- SSH Investigation
- Privilege Escalation Detection
- Incident Documentation
- Digital Forensics Basics

---

## Disclaimer

This project was created for educational purposes inside an isolated virtual lab.
