# 🧠 Detection Analysis Findings

## 📌 Overview

This document outlines the key findings observed during the analysis of endpoint activity using **Sysmon and Splunk SIEM**.

The goal of this analysis was to identify suspicious behavior that resembles real-world attacker techniques.

---

## 🔍 Observed Activity

The following behaviors were successfully generated and detected:

- System reconnaissance commands
- User enumeration
- Privilege enumeration
- Network discovery
- PowerShell execution
- Persistence mechanisms

---

## ⚠️ Key Security Findings

### 1. Process Execution Visibility

Sysmon Event ID 1 provided full visibility into process creation events.

- All executed commands were logged
- Command-line arguments were captured
- Parent-child relationships were visible

---

### 2. Reconnaissance Detection

Commands such as:

- `whoami`
- `systeminfo`
- `ipconfig`

Were clearly logged and searchable in Splunk.

These commands are commonly used by attackers during initial access and discovery phases.

---

### 3. User & Privilege Enumeration

Commands like:

- `net user`
- `whoami /priv`

Allowed identification of:

- Existing users
- Privilege levels
- Potential escalation paths

---

### 4. Network Activity Analysis

The `netstat` command revealed:

- Active connections
- Listening ports
- Network communication patterns

This is useful for detecting lateral movement or suspicious outbound traffic.

---

### 5. PowerShell Activity Monitoring

PowerShell execution was successfully logged, including:

- Command execution
- Script behavior
- Parent process relationships

PowerShell is commonly abused by attackers for stealth operations.

---

### 6. Persistence Detection

Scheduled tasks created using `schtasks` were detected.

This demonstrates the ability to identify:

- Persistence mechanisms
- Unauthorized task creation
- Long-term attacker footholds

---

## 🎯 Detection Summary

This lab confirms that:

- Endpoint telemetry can effectively detect attacker behavior
- Sysmon provides detailed visibility into system activity
- Splunk enables fast searching, correlation, and analysis

---

## 🚀 Analyst Takeaway

A SOC Analyst can use this data to:

- Identify suspicious commands
- Investigate attacker behavior
- Correlate events across the system
- Detect early-stage compromise
