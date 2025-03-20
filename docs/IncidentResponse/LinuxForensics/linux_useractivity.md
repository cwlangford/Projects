# Linux User Activity
## Auth.log
Auth.log contains authentication a trove of information that can be used when analysing unauthorised access and user activity. 
### **Forensic Value**
- **Login Attempts:** Records successful and failed login attempts, including usernames, source IPs, and timestamps. This can help identify brute-force attacks and unauthorised access.
- **Authentication Methods:** Records the authentication method used (e.g. password, SSH keys). This can help understand how the attacker gained access.
- **User Account Changes:** Records user account creation, deletion, and password changes. This can reveal unusual activity such as the creation of a backdoor account.
- **Privilege Escalation:** Records `sudo` usage, and the commands that have been executed with elevated privileges.
- **Service Restarts:** Records services that are restarted. This can be useful when identifying malicious activity or system instability.
- **SSH Activity:** Logs SSH connections, including source and destination IPs, usernames, and authentication states. This is useful for investigation remote access and lateral movement.

### Analysing Auth.log
`auth.log` is a plan-text file and can be accessed using any standard text editor or via the terminal.

**Artefact Location(s):**

```shell
/var/log/auth.log
```

**Useful Commands:**
```shell
#Print contents to terminal
cat auth.log 

#Grep succesful logins
cat auth.log | grep "Accepted password"

#Grep failed logins
cat auth.log | grep "Failed password" 

#Grep successful and failed logins
cat auth.log | grep -E "Accepted password|Failed password"

#Grep sudo activity
cat auth.log | grep "sudo" 
```
