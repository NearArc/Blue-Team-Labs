# SOC Incident Report – SSH Brute Force Activity

---

## Executive Summary
A brute force attack targeting SSH authentication was identified after ingesting Linux authentication logs into Splunk Enterprise. Multiple external IPs attempted repeated SSH logins using both valid and invalid usernames. No successful logins occurred. This incident represents a credential access attempt aligned with MITRE ATT&CK technique T1110 (Brute Force).

---

## Detection Details
**Date Analyzed:** <Insert Date>  
**Log Source:** Linux `/var/log/auth.log`  
**SIEM:** Splunk Enterprise  
**Detection Type:** Authentication Anomaly  
**Severity:** Medium  
**Tactic:** Credential Access  
**Technique:** T1110 – Brute Force  

---

## Findings

### High-Volume Login Failures
A large number of failed login attempts were recorded within a short time window, consistent with automated SSH brute force tools.

### Multiple Attacking IPs
Numerous external IP addresses were involved in the brute force activity. The volume and distribution of attacks indicated scanning/botnet activity rather than a targeted threat actor.

### Username Probing
Attackers attempted both valid and invalid usernames, including:
- root  
- admin  
- guest  
- test  
- random user strings  

### No Successful Logins
A search for accepted logins returned zero results:

index=* "Accepted password"

This confirms that the brute force attack did not compromise the system.

---

## Dashboard Panels Used
To analyze activity, the following dashboard panels were used:

- **Top Attacking IPs**  
- **Attempted Usernames**  
- **Unknown User Attempts**  
- **SSH Failures Over Time**  
- **Attacker IP Activity Timeline**  
- **Successful Login Verification**

These visualizations made it easy to identify patterns and validate that no unauthorized access occurred.

---

## MITRE ATT&CK Mapping
| Tactic | Technique | Description |
|--------|-----------|-------------|
| Credential Access | **T1110 – Brute Force** | Attempting multiple passwords or usernames to gain unauthorized access |

---

## Recommendations

### 1. Enforce Key-Based SSH Authentication  
Disable password logins entirely to prevent brute force success.

### 2. Deploy Fail2ban  
Automatically block repeated failed attempts from the same IP address.

### 3. Firewall Rate Limiting  
Rate-limit SSH connection attempts to slow attackers.

### 4. Move SSH Port (Optional)  
Changing the default SSH port reduces noise but is not a security control.

### 5. Enable Continuous Monitoring  
Configure alerts for:
- Excessive failed logins  
- New IPs attempting root access  
- Repeated authentication attempts within short intervals  

---

## Conclusion
This event was a brute force attack targeting SSH services. No compromise occurred, but the activity highlights the importance of continuous monitoring and brute force protections such as fail2ban and key-based authentication. Detection logic and dashboards created during this investigation can be reused for ongoing monitoring and SOC workflows.



