\# 🔍 Endpoint Activity Analysis Report



\## 📌 Overview



This analysis investigates endpoint activity collected using \*\*Sysmon\*\* and analyzed through \*\*Splunk SIEM\*\*. The objective was to simulate attacker behavior and validate detection capabilities within a monitored Windows environment.



The focus of this investigation includes:



\- Command execution monitoring

\- System and user enumeration

\- Privilege inspection

\- Network activity observation

\- Persistence mechanisms



\---



\## 🧠 Investigation Summary



Simulated attacker activity was executed using native Windows utilities. All activity was successfully captured by Sysmon and ingested into Splunk for analysis.



The investigation confirms that endpoint telemetry provides deep visibility into attacker behavior, even when using legitimate system tools.



\---



\## 🔎 Key Observations



\### 1. Process Creation Monitoring (Sysmon Event ID 1)



\- All executed commands were logged as process creation events

\- Sysmon provided visibility into:

&#x20; - Executable name (Image)

&#x20; - Command-line arguments

&#x20; - User context



This allowed precise identification of each simulated attack action.



\---



\### 2. System Reconnaissance Activity



The following commands were executed and detected:



\- `whoami.exe` → user identification

\- `systeminfo.exe` → system reconnaissance

\- `ipconfig.exe` → network configuration discovery



These commands are commonly used during the \*\*initial reconnaissance phase\*\* of an attack.



\---



\### 3. User Enumeration



\- `net.exe` was used to enumerate user accounts

\- Detection confirmed visibility into user discovery techniques



This behavior aligns with \*\*post-compromise enumeration activity\*\*.



\---



\### 4. Privilege Enumeration



\- `whoami /priv` exposed available privileges

\- This activity is typically used by attackers to identify escalation opportunities



This represents \*\*privilege reconnaissance\*\*, a critical stage before escalation attempts.



\---



\### 5. Network Activity Discovery



\- `netstat.exe` provided visibility into active network connections

\- This can be used by attackers to identify:

&#x20; - Open ports

&#x20; - Established connections

&#x20; - Potential lateral movement paths



\---



\### 6. PowerShell Execution



\- PowerShell activity was successfully logged and detected

\- PowerShell is frequently used in \*\*fileless attacks\*\* and \*\*living-off-the-land techniques\*\*



This represents a \*\*high-risk activity\*\* in real environments.



\---



\### 7. Persistence Mechanism Detection



\- A scheduled task was created using `schtasks.exe`

\- This simulates a common persistence technique



Detection confirmed:



\- Command execution

\- Persistence behavior visibility

\- Ability to track scheduled task creation



\---



\## ⚠️ Risk Assessment



| Activity | Risk Level | Description |

|--------|--------|-------------|

| Command Execution | Medium | Initial system interaction |

| Reconnaissance | Medium | Information gathering phase |

| Privilege Enumeration | High | Potential escalation |

| PowerShell Usage | High | Common attack vector |

| Persistence Creation | Critical | Maintains long-term access |



\---



\## 🧾 Conclusion



The environment successfully captured and detected all simulated attacker behaviors.



This demonstrates that:



\- Sysmon provides detailed endpoint telemetry

\- Splunk enables efficient log analysis and correlation

\- Command-line visibility is essential for detection

\- Even legitimate tools can indicate malicious intent



This lab reflects real-world SOC monitoring scenarios and highlights the importance of behavioral detection techniques.

