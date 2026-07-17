# Incident Report

## Incident Information

| Field | Value |
|-------|-------|
| Incident Type | Privilege Escalation Attempt |
| Severity | Medium |
| Status | Investigated |
| Environment | Isolated Virtual Lab |
| Operating System | Ubuntu Server |
| Log Source | /var/log/auth.log |

---

## Executive Summary

A user named **Afreen** successfully logged into the Ubuntu server through SSH from IP address **192.168.81.128**.

Following authentication, several privilege escalation techniques were attempted, including checking sudo permissions, switching to the root account, accessing restricted files, and enumerating SUID binaries.

Authentication log analysis confirmed that every privilege escalation attempt failed and no unauthorized root access was achieved.

---

## Timeline

| Event | Description |
|-------|-------------|
| SSH Login | Successful login using Afreen account |
| Enumeration | User and privilege information collected |
| Sudo Check | No sudo privileges available |
| su Attempt | Authentication failed |
| Restricted Access | Access denied to `/etc/shadow` and `/root` |
| SUID Enumeration | Standard SUID binaries discovered |
| Logout | SSH session closed normally |

---

## Investigation Findings

- Successful SSH authentication.
- No sudo permissions.
- Failed root authentication.
- No successful privilege escalation.
- Root account remained secure.

---

## Conclusion

The investigation determined that the attacker successfully accessed the system using a valid user account but failed to obtain elevated privileges.

The authentication logs provided sufficient evidence to reconstruct the activity and confirm that the system's privilege controls prevented unauthorized administrative access.
