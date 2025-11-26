# Blue Team Lab

![Status](https://img.shields.io/badge/Project-Active-brightgreen?style=for-the-badge)
![Learning](https://img.shields.io/badge/Focus-Detection%20Engineering-blue?style=for-the-badge)
![Splunk](https://img.shields.io/badge/Tools-Splunk%20Enterprise-orange?style=for-the-badge)
![SOC](https://img.shields.io/badge/Role-SOC%20Analysis-purple?style=for-the-badge)

This repo contains my blue team and defensive security work. Everything here is built using real logs, Splunk Enterprise, and hands-on investigations.  
The goal is to understand attacker behavior by analyzing events, writing SPL searches, building dashboards, and documenting incidents the way real SOC analysts do.

---

## Projects

### SSH Brute Force Detection in Splunk
![Progress](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat-square)

I ingested real Linux SSH logs into Splunk and investigated brute force activity from external IP addresses.  
I built a dashboard showing:

- Top attacking IPs  
- Usernames attempted  
- Unknown user attempts  
- SSH failures over time  
- Attacking IP activity over time  
- Successful login checks  

Includes screenshots, SPL queries, and incident handler notes.

Located in the `ssh-bruteforce-splunk` folder.

---

## Upcoming Projects

### Windows Event Log Detection  
Failed RDP, security event analysis, Sysmon 13/1/11 correlation.

### MITRE ATT&CK Mapping  
Mapping detections to MITRE techniques like T1110 (Credential Access).

### Suricata IDS Alert Analysis  
PCAP import → alert review → threat breakdown.

### Sigma Rule Development  
Writing Sigma rules for SSH brute force and Windows authentication anomalies.

---
