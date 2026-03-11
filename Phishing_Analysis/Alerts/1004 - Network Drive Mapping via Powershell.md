# 1004 - Network Drive Mapping via Powershell

## Process Evidence
**Parent Process:** powershell.exe  
**Child Process (spawned):** net.exe  
**Host:** win-3450  
**Working Directory:** C:\Users\michael.ascot\downloads\  
**Event Action:** Process Create (rule: ProcessCreate)  
**Data Source:** Sysmon  

---

## Incident Analysis
**Time of Activity:** Mar 11th 2026 at 09:57  
**Affected Entity:** win-3450 (host), user: michael.ascot  

### Reason for Classifying as False Positive
* Mapping a network drive using `net.exe` is a standard Windows operation.  
* Powershell execution in this context is normal and does not indicate malicious activity.  
* No unusual file access or lateral movement detected.  
* Network share (`\\FILESRV-01\SSF-FinancialRecords`) is authorized for this user.  

### Reason for Escalating the Alert
* N/A  

---

## List of Attack Indicators
* Parent process: powershell.exe  
* Child process: net.exe  
* Network share mapped: `\\FILESRV-01\SSF-FinancialRecords`  
* Command executed from working directory: `C:\Users\michael.ascot\downloads\`  

---

## Case Summary
This alert was triggered by a network drive mapping via Powershell. After investigation, the activity is considered **legitimate user behavior**, as there are no signs of malicious activity or unauthorized access.  

The alert is classified as **False Positive**. Recommended actions include confirming with the user, reviewing logs, and documenting the incident.
