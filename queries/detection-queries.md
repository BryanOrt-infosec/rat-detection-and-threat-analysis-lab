# 🔍 Splunk Detection Queries

## 📌 Overview

This document contains Splunk queries used to detect simulated attacker activity based on Sysmon logs.

All queries use:

- index: main
- sourcetype: XmlWinEventLog:Microsoft-Windows-Sysmon/Operational

---

## 🔎 View All Sysmon Logs

```spl
index=main sourcetype="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational"
🎯 Detect whoami Execution
index=main sourcetype="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" CommandLine="*whoami*"
🌐 Detect ipconfig (Network Discovery)
index=main sourcetype="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" CommandLine="*ipconfig*"
👤 Detect net.exe (User Enumeration)
index=main sourcetype="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" CommandLine="*net*"
🌍 Detect netstat (Network Connections)
index=main sourcetype="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" CommandLine="*netstat*"
⚡ Detect PowerShell Execution
index=main sourcetype="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" Image="*powershell.exe"
🔒 Detect Scheduled Tasks (Persistence)
index=main sourcetype="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" CommandLine="*schtasks*"
📊 Count Events by Command
index=main sourcetype="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational"
| stats count by CommandLine
| sort -count
