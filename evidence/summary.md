# 📂 Evidence Summary

## 📌 Overview

This document provides a summary of all collected evidence during the endpoint detection lab using Sysmon and Splunk.

The evidence supports detection of simulated attacker activity.

---

## 🖥️ Command Execution Evidence

The following commands were executed and captured:

- whoami
- systeminfo
- net user
- whoami /priv
- PowerShell commands
- Get-Process

These commands simulate attacker reconnaissance and enumeration techniques.

---

## 📡 Sysmon Evidence

Sysmon successfully logged:

- Process creation (Event ID 1)
- Command-line arguments
- Parent process relationships

This confirms proper Sysmon configuration and logging.

---

## 🔍 Splunk Evidence

Splunk successfully ingested and displayed logs for:

- whoami execution
- ipconfig network discovery
- net.exe user enumeration
- netstat connection analysis
- PowerShell execution
- schtasks persistence creation

Each activity was searchable and correlated within Splunk.

---

## 📊 Detection Evidence

Statistical and search-based analysis in Splunk showed:

- Clear identification of executed commands
- Ability to filter by command-line activity
- Visibility into user behavior patterns
- Detection of persistence techniques

---

## 📸 Screenshot Evidence

The following screenshots support the analysis:

1. Command execution (whoami, systeminfo, etc.)
2. Sysmon log ingestion
3. Splunk search results for each command
4. Detection of persistence activity

---

## 🎯 Conclusion

The collected evidence demonstrates that:

- Endpoint activity is fully visible using Sysmon
- Splunk can detect and analyze attacker-like behavior
- Logs provide sufficient detail for investigation

This validates the effectiveness of endpoint monitoring and SIEM-based detection.
