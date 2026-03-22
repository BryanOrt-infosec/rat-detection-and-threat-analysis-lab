\# 🔎 Splunk Detection Queries



\## 📌 Overview



The following queries were used to detect and analyze endpoint activity generated during the lab. All queries leverage Sysmon logs ingested into Splunk.



\---



\## 🟢 Sysmon Log Ingestion



```spl

index=main sourcetype=XmlWinEventLog:Microsoft-Windows-Sysmon/Operational

🟢 Process Creation Events (Event ID 1)

index=main EventCode=1

🟢 Command Execution Visibility

index=main EventCode=1

| table \_time Image CommandLine User

| sort -\_time

🟢 whoami Detection

index=main "whoami.exe"

🟢 ipconfig Detection

index=main "ipconfig.exe"

🟢 net.exe Detection (User Enumeration)

index=main "net.exe"

🟢 netstat Detection (Network Activity)

index=main "netstat.exe"

🟢 PowerShell Detection

index=main Image="\*powershell\*"

🟢 Scheduled Task Detection (Persistence)

index=main "schtasks.exe"

🟢 Process Frequency Analysis

index=main EventCode=1

| stats count by Image

| sort -count

