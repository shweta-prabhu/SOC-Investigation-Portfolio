## Email Evidence

**Sender:** [eileen@trendymillineryco.me](mailto:eileen@trendymillineryco.me)
**Recipient:** [support@tryhatme.com](mailto:support@tryhatme.com)
**Subject:** Inheritance Alert: Unknown Billionaire Relative Left You Their Hat Fortunes

**Email Body:**

> A long lost billionaire relative has left you their secret hat empire.
> To claim your inheritance send us your banking details immediately.

---

## Incident Analysis

**Time of Activity:** Mar 11th 2026 at 09:23

**Affected Entity:**

* [support@tryhatme.com](mailto:support@tryhatme.com)

---

### Reason for Classifying as True Positive

* The email requests sensitive banking information, which is a strong indicator of phishing and potential fraud.

---

### Reason for Escalating the Alert

* N/A

---

### Recommended Remediation Actions

* Block the sender address **[eileen@trendymillineryco.me](mailto:eileen@trendymillineryco.me)**.
* Add the domain **trendymillineryco.me** to the organization’s email blocklist.
* Search email logs to determine whether other users received the same phishing email.
* Notify the affected user and advise them not to respond or provide any personal information.

---

### List of Attack Indicators

* Suspicious sender email: `eileen@trendymillineryco.me`
* Suspicious domain: `trendymillineryco.me`
* Phishing subject line: *Inheritance Alert: Unknown Billionaire Relative Left You Their Hat Fortunes*

---

## Case Summary

This alert was triggered after an inbound email from the external domain **trendymillineryco.me** was detected. The message attempted to lure the recipient with a fraudulent inheritance claim and requested sensitive banking information.
Analysis confirmed multiple phishing indicators, including the use of an unfamiliar external domain, social engineering language, and a request for financial details. Based on these indicators, the alert was classified as a **True Positive phishing attempt**.

The recommended response includes blocking the sender and domain, reviewing email logs for similar messages, and notifying the affected user to prevent potential credential or financial compromise.
