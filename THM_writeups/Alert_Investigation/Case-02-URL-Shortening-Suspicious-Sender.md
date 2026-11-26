## Case 02 - URL Shortening Suspicious Sender

### Alert Information
<img width="719" height="359" alt="Screenshot 2026-09-17 095210" src="https://github.com/user-attachments/assets/14d2ab51-f60f-4e00-8b3c-ae70751fe2eb" />

**List of affected entities:**
- Recipient: `h.harris@thetrydaily.thm`
- IP: `10.20.2.17`
- Host: `win-3457`

**List of attack indicators:**
- Sender: `urgents@amazon.biz` <br>
- URL: `http://bit.ly/3sHkX3da12340`<br>
- Destination IP of the URL: `67.199.248.11`

### Investigation & Analysis
The alert indicated that `urgents@amazon.biz` sent an email to `h.harris@thetrydaily.thm` regarding an incomplete shipping address that needed to be filled out and the message appeared to be urgent, at 09/17/2026 03:47. The email contained a suspicious URL shortener: `http://bit.ly/3sHkX3da12340`, with the intent of getting `h.harris@thetrydaily.thm` to open the URL.

The URL was analyzed using TryDetectThis and flagged as MALICIOUS.<br>
<img width="652" height="274" alt="Screenshot 2026-09-17 095538" src="https://github.com/user-attachments/assets/cec31998-4e47-4cc0-ab2f-69f27d00d914" />

It was also discovered that the URL leads to an unknown IP address: 67.199.248.11, which was also flagged as MALICIOUS.<br>
<img width="654" height="271" alt="Screenshot 2026-09-17 095605" src="https://github.com/user-attachments/assets/8d2b73fc-de77-4337-a4cf-dc2513ac49e6" />

This activity potentially indicates a phishing email and a malicious URL related to Spearphishing Link T1598.003 in MITRE ATTACK.

### Classification & Escalation
| Classification     | Escalation          |
|--------------------|---------------------|
| True Positive (TP) | Escalation is needed for further investigation |

### Final Asessment
Based on the available evidence and analysis, this alert is classified as a **True Positive**. The associated URL and destination IP address that have been analyzed are assessed as MALICIOUS by TryDetectThis. This activity indicates a Phishing Email attack containing a malicious URL related to Spearphishing Link T1598.003 in the MITRE ATTACK.

Escalation is required for further investigation to determine whether there is outbound traffic, whether the user attempted to access the URL, or whether the host/account has been compromised.

### Remediation Recommendations
No immediate remediation is required at this time.

Monitoring will continue to detect any other suspicious indicators while this case is further analyzed. Further mitigation or remediation actions should be considered if subsequent analysis confirms the presence of malicious activity.
