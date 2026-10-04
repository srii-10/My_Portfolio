## Investigation Report Login

### Alert Information
<img width="903" height="185" alt="1" src="https://github.com/user-attachments/assets/461769ac-de76-4e0c-bbb5-52236eda96cb" />

**List of entities involved:**
- Suspicious IP: `221.181.185.159`
- Port: `22 (SSH)`
- Timestamp: `25/09/2026 13:23` & `25/09/2026 13:27`

### Investigation & Analysis
At 25/09/2026 13:23, an alert appeared indicating unauthorized login attempts from IP address `221.181.185.159` via port `22 (SSH)`. Four minutes later, at 25/09/2026 13:27, a successful login was detected from the same suspicious IP address via the SSH port.

An investigation of the suspicious IP address was then conducted using the provided IP Hunter tool.
<img width="466" height="265" alt="2" src="https://github.com/user-attachments/assets/d46b40ba-ab19-45c2-9c36-a8a15ead5ff4" />

It has been confirmed that this IP address is malicious and is listed in the company’s database. Below is information regarding this malicious IP address.
<img width="518" height="251" alt="3" src="https://github.com/user-attachments/assets/14ee180c-e58c-4a41-944f-2f6e5a7494d7" />

### Severity & Escalation
| **Severity** | Classification     | Escalation                               |
|--------------|--------------------|------------------------------------------|
| Critical     | True Positive (TP) | Further analysis and action are required |

### Final Assessment
Based on the investigation and analysis of the available evidence, the event indicates a potential successful brute-force attack, as multiple failed login attempts from a known malicious IP were followed by a successful login from the same IP within a short time window. This behavior suggests a potential account compromise.

The IP address has been blocked, further action and analysis are needed to determine whether any related activity occurred after the account was compromised.

### Remediation Recommendation

