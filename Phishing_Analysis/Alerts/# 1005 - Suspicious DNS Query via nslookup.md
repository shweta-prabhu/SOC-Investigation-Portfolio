# 1005 - Suspicious DNS Query via nslookup

## Process Evidence
**Parent Process:** powershell.exe  
**Child Process (spawned):** nslookup.exe  
**Host:** win-3450  
**User:** michael.ascot  
**Working Directory:** C:\Users\michael.ascot\downloads\exfiltration\  
**Event Action:** Process Create (rule: ProcessCreate)  
**Data Source:** Sysmon  

---

## Incident Analysis
**Time of Activity:** Mar 11th 2026 at 09:58  
**Affected Entity:** win-3450 (host), user: michael.ascot  

### Reason for Classifying as True Positive
* `nslookup.exe` was executed via PowerShell from an unusual working directory.  
* The queried domain (`U3VtbWFyeS54bHN4c87JTM0rCcgvKk.haz4rdw4re.io`) is random-looking and suspicious, indicating potential **DNS-based data exfiltration** or **malicious C2 activity**.  
* Parent-child relationship (PowerShell → nslookup.exe) is uncommon for normal user behavior.  

### Reason for Escalating the Alert
* Potential **data exfiltration** from the host.  
* Possible **host compromise**, requiring Tier 2 SOC / Incident Response investigation.  

---

## Recommended Remediation Actions
* Isolate the host `win-3450`.  
* Capture logs of PowerShell and nslookup execution.  
* Investigate the suspicious domain for reputation and C2 activity.  
* Check for similar DNS queries across the network.  
* Escalate to Incident Response / SOC Tier 2 for containment and further investigation.  

---

## List of Attack Indicators
* Parent process: powershell.exe  
* Child process: nslookup.exe  
* Suspicious DNS query: `U3VtbWFyeS54bHN4c87JTM0rCcgvKk.haz4rdw4re.io`  
* Working directory: `C:\Users\michael.ascot\downloads\exfiltration\`  
* Uncommon parent-child process relationship for normal operations  

---

## Case Summary
This alert was triggered by `nslookup.exe` being executed via PowerShell to query a suspicious, random-looking domain. The activity is classified as **True Positive**, potentially indicating **DNS-based data exfiltration** or a malicious command-and-control channel.  

Recommended actions include isolating the host, capturing logs, analyzing the domain, and escalating to Incident Response for investigation.
