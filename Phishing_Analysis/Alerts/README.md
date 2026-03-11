# Alerts Folder

This folder contains SOC lab alert reports in Markdown format. Each file represents a security event detected in the environment, including phishing emails, suspicious processes, and potential data exfiltration activities.

## Purpose

The alerts in this folder are used to:

* Document security incidents in detail.
* Provide a case summary for each alert.
* Recommend remediation and escalation actions.
* Serve as a reference for SOC analysis, training, and lab exercises.

## Contents

| Alert File | Description | Classification |
|------------|-------------|----------------|
| 1001-Suspicious Email from External Domain.md | Phishing email attempting to steal banking information | True Positive |
| 1002-Suspicious Process with Uncommon Parent-Child Relationship.md | Suspicious Windows process spawned by an uncommon parent | False Positive |
| 1003-Suspicious Attachment Found in Email.md | Email containing a potentially malicious attachment | True Positive |
| 1004-Network Drive Mapping via Powershell.md | Network drive mapped via PowerShell | False Positive |
| 1005-Suspicious DNS Query via nslookup.md | nslookup executed via PowerShell to query a suspicious domain | True Positive |

## How to Use

* Open each Markdown file to view **alert details**, including process evidence, incident analysis, attack indicators, and remediation actions.  
* Use these reports as a **reference for SOC investigations** and threat hunting exercises.  
* Follow recommended remediation actions for **True Positive alerts** to prevent potential compromise.  
