# Advanced-Detection-Engineering-Project
 Breach Scenario Summary: Detection & Response

This README describes a simulated incident response scenario for a **suspected breach involving credential theft**, using:
- Splunk SPL detections
- Python-based automated remediation

---

##  Scenario Overview
> A user logs in remotely via RDP after business hours. Immediately after, encoded PowerShell is executed on the same host to download and execute a script. Within minutes, the attacker attempts to access the LSASS process — a classic sign of credential dumping.

This scenario replicates a **real-world attack chain**, often seen in:
- Ransomware intrusions
- Penetration testing engagements
- Post-exploitation in lateral movement campaigns
-  Remediation Actions Taken

###  1. Isolate Host via EDR API
- **Script**: `isolate_host.py`
- **Purpose**: Prevent lateral movement and cut off attacker access
- **Method**: Sends API call to endpoint detection and response (EDR) platform

###  2. Disable Suspicious User Account
- **Script**: `alert_and_disable_user.py`
- **Purpose**: Stop attacker from using stolen or reused credentials
- **Method**: Uses local command to disable the user account

---

##  Final Summary
This breach scenario simulates a common Windows-based compromise involving:
1. **Initial access** via RDP
2. **Execution** of an obfuscated payload
3. **Credential dumping** from LSASS
