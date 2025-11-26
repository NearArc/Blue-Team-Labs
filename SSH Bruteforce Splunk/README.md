# SSH Brute Force Detection in Splunk

![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![Splunk](https://img.shields.io/badge/SIEM-Splunk%20Enterprise-orange?style=for-the-badge)
![BlueTeam](https://img.shields.io/badge/Category-Blue%20Team-blue?style=for-the-badge)
![MITRE](https://img.shields.io/badge/MITRE-T1110%20Brute%20Force-lightgrey?style=for-the-badge)

This project analyzes a real SSH brute force attack using Splunk Enterprise. I ingested Linux SSH logs, built searches to detect malicious activity, and created a dashboard that visualizes attacker behavior.  
The goal of the project is to learn SIEM analysis, SPL queries, brute force detection patterns, and how to document incidents like a SOC analyst.

---

## Dashboard Preview
(Place your `dashboard.png` screenshot here)

---

## What This Project Covers

### ✔ Log Ingestion
- Uploaded real `/var/log/auth.log` files  
- Applied correct source type and host fields  
- Validated SSH event visibility in Splunk

### ✔ Detection Engineering
- Identified top attacking IP addresses  
- Detected brute force attempts using SPL  
- Extracted usernames (valid and invalid)  
- Counted SSH failures over time  
- Confirmed no successful logins  

### ✔ Dashboard Creation
Panels built:

- **Top Attacking IPs**
- **Attempted Usernames**
- **Unknown User Attempts**
- **SSH Failures Over Time**
- **Attacker IP Activity Timeline**
- **Successful Login Check**

### ✔ MITRE ATT&CK Mapping
This activity maps to:

**Tactic:** Credential Access  
**Technique:** T1110 – Brute Force  

---

## Project Files

| File | Description |
|------|-------------|
| `queries.md` | All SPL queries for detections and dashboard panels |
| `notes.md`   | Investigation notes, findings, indicators |
| `report.md`  | Full SOC-style incident report |
| `dashboard.png` | Screenshot of the dashboard |

---

## Skills Demonstrated

- SIEM data ingestion  
- SPL query building  
- Brute force detection  
- SSH authentication analysis  
- Dashboard design  
- Incident documentation  
- MITRE ATT&CK mapping  

---

## Next Steps

This is the first project in my Blue Team Lab.  
Upcoming additions:

- RDP brute force detection  
- Windows Event Log analysis (4624/4625)  
- Sysmon correlation (ProcessCreate / NetworkConnect)  
- Suricata IDS alert analysis  
- Sigma rule development  

