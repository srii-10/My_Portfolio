## Case 03 - Blacklisted External URL Firewall

### Alert Information
<img width="716" height="381" alt="Screenshot 2026-09-17 095243" src="https://github.com/user-attachments/assets/639e6ab0-8368-4c1c-a848-991a7fe94a1d" />

**List of affected entities:**
- Source IP: `10.20.2.17`
- User: `h.harris@thetrydaily.thm`
- Host: `win-3457`

**List of indicator entities:**
- Destination IP: `67.199.248.11`
- Destination port: `80` (HTTP)
- URL: `http://bit.ly/3sHkX3da12340`

### Investigation & Analysis
At 09/17/2026 03:49, the firewall detected that the internal IP address `10.20.2.17` attempted to access the URL `http://bit.ly/3sHkX3da12340` on port `80`, with the destination IP address `67.199.248.11`. The internal IP address is associated with the affected entities: user `h.harris@thetrydaily.thm` and host `win-3457`.

The URL is on the company's blacklist because it has been flagged as MALICIOUS by TryDetectThis.<br>
<img width="652" height="274" alt="Screenshot 2026-09-17 095538" src="https://github.com/user-attachments/assets/25a7a366-1a7a-4a12-b341-0bc966854071" />

The destination IP address is also flagged as MALICIOUS.<br>
<img width="654" height="271" alt="Screenshot 2026-09-17 095605" src="https://github.com/user-attachments/assets/63fc7fd7-daeb-43f0-be94-ca602444bb56" />

The alert is linked to a previously identified phishing email that targeted the same user a few minutes ago. The user attempted to access the malicious URL, but the connection was blocked by the firewall. No evidence of a successful compromise was found during the investigation.

### Classification & Escalation
| Classification     | Escalation   |
|--------------------|--------------|
| True Positive (TP) | Not required |

### Final Assessment
The alert is classified as a **True Positive** because the destination URL and IP address are identified as MALICIOUS by TryDetectThis and the firewall detected an attempted connection to the destination.

The connection was successfully blocked by the firewall and no evidence of successful compromise was identified within the available telemetry. Based on the available evidence, no escalation is required at this time.

Continued monitoring is recommended for any subsequent suspicious activity involving the affected user or host.

### Remediation Recommendation
No remediation action is required.
