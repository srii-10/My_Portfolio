## Investigation Report Login

### Alert Information
<img width="903" height="185" alt="1" src="https://github.com/user-attachments/assets/461769ac-de76-4e0c-bbb5-52236eda96cb" />

**List of entities involved:**
- Suspicious IP: `221.181.185.159`
- Port: `22 (SSH)`
- Timestamp: `25/09/2026 13:23` & `25/09/2026 13:27`

### Investigation & Analysis
At 25/09/2026 13:23, an alert appeared indicating unauthorized login attempts from IP address `221.181.185.159` via port `22 (SSH)`.

Four minutes later, at 25/09/2026 13:27, a successful login was detected from the same suspicious IP address through SSH. The correlation between the failed login attempts and the subsequent successful login from the same source IP indicates suspicious authentication activity and raises the possibility of a successful brute-force attack.

An investigation of the suspicious IP address was then conducted using the provided IP Hunter tool. <br>
<img width="466" height="265" alt="2" src="https://github.com/user-attachments/assets/d46b40ba-ab19-45c2-9c36-a8a15ead5ff4" /> <br>

The investigation confirmed that this IP address was identified as a malicious IP address and was listed in the company's database. Below is information regarding this malicious IP address. <br>
<img width="518" height="251" alt="3" src="https://github.com/user-attachments/assets/14ee180c-e58c-4a41-944f-2f6e5a7494d7" />

### Severity & Escalation
| **Severity** | Classification     | Escalation                               |
|--------------|--------------------|------------------------------------------|
| Critical     | True Positive (TP) | Further analysis and action are required |

The alert was classified **True Positive (TP)** based on the malicious IP reputation and the successful login following multiple unauthorized attempts.

The incident was escalated to the right person according to the SOC escalation procedure. <br>
<img width="613" height="381" alt="4" src="https://github.com/user-attachments/assets/ab789c2f-9489-483b-bfe6-79cc532e3e04" />

### Containment
Following the investigation and escalation process, the malicious IP address `221.181.185.159` was blocked on the firewall as an initial containment action, in accordance with authorization from the SOC Team Lead. <br>
<img width="836" height="395" alt="5" src="https://github.com/user-attachments/assets/610043d0-3bf6-4b42-bca4-b5c3acef0d78" />
<img width="771" height="205" alt="6" src="https://github.com/user-attachments/assets/89224308-9f13-4134-8689-fd4d94d467bb" />

### Final Assessment
Based on the investigation and analysis of the available evidence, the event indicates a potential successful brute-force attack, as multiple failed login attempts from a known malicious IP were followed by a successful login from the same IP within a short time window. This behavior suggests a potential account compromise.

The IP address has been blocked, further action and analysis are needed to determine whether any related activity occurred after the account was compromised.
