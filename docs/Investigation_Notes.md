# Investigation Notes

## Objective

The objective of this investigation was to analyze Linux authentication logs after simulating a privilege escalation attempt in an isolated virtual lab.

---

## Scenario

A user named **Afreen** successfully authenticated to the Ubuntu server through SSH.

After gaining access, the user attempted several privilege escalation techniques commonly observed during post-compromise activities.

The investigation focused on determining whether the attacker successfully obtained elevated privileges.

---

## Observed Activities

The following actions were observed during the investigation:

- Successful SSH login.
- User and privilege enumeration.
- Verification of sudo permissions.
- Attempt to switch to the root account using `su`.
- Attempt to access restricted files and directories.
- Enumeration of SUID binaries.
- Logout from the system.

---

## Evidence Collected

Evidence collected from **/var/log/auth.log** included:

- Successful SSH authentication.
- Session creation and termination.
- Failed `su` authentication.
- Denied sudo privileges.
- SSH connection history.
- Source IP address.
- Target username.

---

## Findings

The investigation confirmed that:

- SSH authentication was successful.
- The account had no administrative privileges.
- All privilege escalation attempts failed.
- No successful root authentication was detected.
- No evidence of unauthorized root access was found.

---

## Indicators

| Indicator | Value |
|-----------|-------|
| Source IP | 192.168.81.128 |
| Target User | Afreen |
| Service | SSH |
| Log File | /var/log/auth.log |

---

## Conclusion

The attacker successfully gained access using a valid user account but failed to escalate privileges.

Linux authentication logs clearly documented every important event, allowing the investigation to reconstruct the attack timeline and verify that the system's privilege controls successfully prevented unauthorized root access.
