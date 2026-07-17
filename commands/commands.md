# Commands Used

This file lists the commands used during the Privilege Escalation Investigation lab.

| Command | Purpose |
|---------|---------|
| `sudo adduser Afreen` | Create a new user account. |
| `sudo truncate -s 0 /var/log/auth.log` | Clear the authentication log before starting the investigation. |
| `sudo systemctl restart ssh` | Restart the SSH service. |
| `sudo systemctl status ssh` | Verify that the SSH service is running. |
| `ip a` | Display network interfaces and IP addresses. |
| `nmap -sV 192.168.81.129` | Scan the target machine and identify open ports and service versions. |
| `ssh Afreen@192.168.81.129` | Connect to the target system via SSH. |
| `hostname` | Display the system hostname. |
| `whoami` | Display the current logged-in user. |
| `id` | Display user ID and group information. |
| `groups` | Show group memberships. |
| `pwd` | Display the current working directory. |
| `sudo -l` | Check available sudo privileges. |
| `su root` | Attempt to switch to the root account. |
| `cat /etc/shadow` | Attempt to read the system password hash file. |
| `cd /root` | Attempt to access the root user's home directory. |
| `sudo ls /root` | Attempt to list the contents of the root directory using sudo. |
| `find / -perm -4000 -type f 2>/dev/null` | Search for SUID binaries. |
| `exit` | Close the SSH session. |
| `grep sudo /var/log/auth.log` | Search for sudo-related events. |
| `grep "su:" /var/log/auth.log` | Search for `su` authentication attempts. |
| `grep "Afreen" /var/log/auth.log` | Display all events related to the Afreen account. |
| `grep "COMMAND=" /var/log/auth.log` | Show commands executed through sudo. |
| `grep sshd /var/log/auth.log` | Display SSH authentication events. |
| `grep "Afreen" /var/log/auth.log \| head -1` | Display the first event involving Afreen. |
| `grep "Afreen" /var/log/auth.log \| tail -1` | Display the last event involving Afreen. |
| `last root` | Check login history for the root account. |
| `grep -oP '(?<=from )(\d{1,3}\.){3}\d{1,3}' /var/log/auth.log \| sort -u` | Extract unique source IP addresses. |
| `grep -E "Accepted\|Failed" /var/log/auth.log \| awk '{for(i=1;i<=NF;i++) if($i=="for") print $(i+1)}' \| sort -u` | Extract targeted usernames from login events. |
| `grep "Authentication failure" /var/log/auth.log` | Search for authentication failure events. |
