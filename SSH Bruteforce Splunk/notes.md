# SSH Brute Force Investigation – Analyst Notes

---

## Log Source
- Linux `/var/log/auth.log`
- Ingested manually into Splunk Enterprise
- Source type verified as "linux_secure"

---

## Summary of Findings
- Multiple external IPs attempted SSH brute forcing
- Majority of attempts targeted the `root` user
- Several attempts used fake usernames:
  - `test`
  - `guest`
  - `admin`
- The highest activity came from a small group of repeating IP addresses
- No successful logins occurred during the window of investigation

---

## Indicators of Brute Force Behavior
- High-volume repeated failures from same IP
- Short time intervals between login attempts
- Attempts across many different usernames
- Pattern matching MITRE technique T1110

---

## Key Indicators (IOCs)

### Top Attacking IPs
- (List from your dashboard)

### Usernames Used
- root
- admin
- guest
- test
- random numeric strings

---

## Timeline Notes
- Attacks occurred over multiple minutes
- Pattern consistent with automated brute-force tools (e.g., Hydra, botnets)

---

## Conclusion
This was a distributed SSH brute-force attack with no successful logins.  
The host resisted the attack due to strong authentication controls.  
Recommended additional steps include fail2ban, key-based authentication, and firewall rate limiting.

