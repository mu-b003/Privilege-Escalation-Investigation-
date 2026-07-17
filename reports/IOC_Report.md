# IOC Report

## Indicators of Compromise

| Indicator | Value |
|-----------|-------|
| Source IP | 192.168.81.128 |
| Target User | Afreen |
| Target Service | SSH |
| Log File | /var/log/auth.log |

---

## Suspicious Activities

- Successful SSH login.
- Multiple privilege escalation attempts.
- Failed sudo execution.
- Failed `su` authentication.
- Attempts to access restricted files.
- Enumeration of SUID binaries.

---

## Detection Evidence

### Authentication

- Accepted password for Afreen

### Privilege Escalation

- Authentication failure for `su`
- sudo access denied

### File Access

- Permission denied: `/etc/shadow`
- Permission denied: `/root`

### Session Activity

- SSH session opened
- SSH session closed

---

## Risk Assessment

| Category | Status |
|----------|--------|
| Initial Access | Successful |
| Privilege Escalation | Failed |
| Persistence | Not Observed |
| Credential Access | Not Observed |
| Root Compromise | Not Detected |

---

## Conclusion

The collected indicators show that the attacker authenticated successfully but was unable to escalate privileges or gain administrative access.

The investigation confirms that the system's security controls effectively prevented unauthorized root access.
