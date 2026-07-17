# Investigation Summary

## Objective

Analyze Linux authentication logs after a simulated privilege escalation attempt.

---

## Summary

The investigation focused on reviewing authentication events generated during a simulated attack.

The user **Afreen** successfully authenticated via SSH and attempted multiple privilege escalation techniques.

Log analysis confirmed that:

- SSH login was successful.
- sudo access was denied.
- `su` authentication failed.
- Access to protected resources was denied.
- No root session was established.

---

## Evidence

- Successful SSH login
- Failed `su` authentication
- Denied sudo privileges
- SSH session opened
- SSH session closed
- Source IP identified

---

## Final Assessment

The attacker successfully authenticated but failed to obtain elevated privileges.

No indicators suggest that the system was fully compromised.
