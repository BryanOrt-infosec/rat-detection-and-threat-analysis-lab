\# 📁 Evidence Summary



\## 📌 Overview



This section documents all evidence collected during the endpoint detection lab. Evidence includes both command execution and corresponding detection results in Splunk.



The goal is to demonstrate a clear relationship between:



\- Simulated attacker actions

\- Logged system activity

\- SIEM-based detection



\---



\## 📸 Evidence Categories



\### 1. Attack Simulation Evidence



These screenshots capture the execution of attacker-like commands:



\- whoami command execution

\- systeminfo system enumeration

\- net user enumeration

\- whoami privilege inspection

\- PowerShell execution

\- Get-Process command



These represent the \*\*attack phase\*\* of the investigation.



\---



\### 2. Log Ingestion Evidence



\- Sysmon ingestion into Splunk confirms that endpoint logs are successfully collected and searchable

\- Demonstrates that the SIEM pipeline is functioning correctly



\---



\### 3. Detection Evidence (Splunk)



These screenshots demonstrate successful detection of:



\- `whoami.exe` execution

\- `ipconfig.exe` network discovery

\- `net.exe` user enumeration

\- `netstat.exe` network connection analysis

\- `powershell.exe` execution

\- `schtasks.exe` persistence mechanism



Each detection validates the ability to identify attacker behavior using log analysis.



\---



\## 🔗 Correlation



The evidence establishes a clear timeline:



1\. Command executed on endpoint

2\. Sysmon logs event

3\. Splunk ingests event

4\. Detection query identifies activity



This correlation demonstrates effective endpoint monitoring and SIEM-based detection.



\---



\## 🎯 Key Takeaways



\- Endpoint telemetry provides high visibility into system activity

\- Legitimate tools can indicate malicious intent

\- SIEM solutions enable rapid detection and investigation

\- Detection queries can be used to identify suspicious behavior patterns



\---



\## 🧾 Conclusion



The collected evidence confirms that all simulated attacker actions were successfully logged and detected.



This validates:



\- Proper Sysmon configuration

\- Successful log ingestion into Splunk

\- Effective detection using SPL queries



The lab demonstrates a complete detection workflow from execution to analysis.

