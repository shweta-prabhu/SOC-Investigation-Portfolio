# 1002 - Suspicious Process with Uncommon Parent-Child Relationship

## Process Evidence

**Parent Process:** services.exe
**Child Process (spawned):** WUDFHost.exe
**Host:** win-3455
**Command Line:**

```
"C:\Windows\System32\WUDFHost.exe" -HostGUID:{24b7eef1-ada5-453b-a5a6-93007dca6fbc} -IoEventPortName:\UMDFCommunicationPorts\WUDF\HostProcess-fd5c32fb-5bb6-4693-82a7-6cec85d58bc4 -SystemEventPortName:\UMDFCommunicationPorts\WUDF\HostProcess-3ba97dd6-3700-4e8a-8921-1e24128d9c7d -IoCancelEventPortName:\UMDFCommunicationPorts\WUDF\HostProcess-2a6ae716-7c20-4d0c-97b6-bb3346775edf -NonStateChangingEventPortName:\UMDFCommunicationPorts\WUDF\HostProcess-54470b14-46b9-4c56-abe1-d9b12ef13c5f -LifetimeId:39d16a20-5092-495b-95b9-c7e0ec216f0f -DeviceGroupId: -HostArg:0"
```

**Working Directory:** C:\Windows\system32\
**Event Action:** Process Create (rule: ProcessCreate)

---

## Incident Analysis

**Time of Activity:** Mar 11th 2026 at 09:41

**Affected Entity:**

* win-3455 (host)
* WUDFHost.exe (child process)
* services.exe (parent process)

---

## Reason for Classifying as False Positive

* WUDFHost.exe is a legitimate Windows system process used for device driver communication.
* Located in the correct system path: C:\Windows\System32\WUDFHost.exe.
* Command line arguments match expected behavior.
* Parent process (services.exe) is legitimate.
* Alert triggered only because of an uncommon parent-child relationship, not due to malicious behavior.

---

## Reason for Escalating the Alert

* N/A

---


## List of Attack Indicators

* Uncommon parent-child process relationship: services.exe → WUDFHost.exe
* Process name: WUDFHost.exe
* Host: win-3455
* Command line includes multiple UMDF communication ports

---

## Case Summary

This alert was triggered after a process creation on host win-3455 was detected. The child process WUDFHost.exe was spawned by services.exe, which is an uncommon parent-child relationship.
Investigation confirmed that WUDFHost.exe is a legitimate Windows system process with expected command-line arguments and path. No suspicious activity was observed.
Based on these findings, the alert is classified as a **False Positive**. Recommended actions include verifying the digital signature, reviewing logs for similar events, and documenting the alert in GitHub for SOC tracking.
