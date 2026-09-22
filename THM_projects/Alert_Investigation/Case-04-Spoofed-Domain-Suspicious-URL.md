## Case 04 - Spoofed Domain Suspicious URL

### Alert Information
<img width="721" height="369" alt="Screenshot 2026-09-17 095315" src="https://github.com/user-attachments/assets/e33d163b-59d0-4f40-8187-2e44fc185709" />

**List of affected entities:**
- Recipient: `c.allen@thetrydaily.thm`
- IP: `10.20.2.25`
- Host: `win-3463`

**List of indicator entities:**
- Sender: `no-reply@m1crosoftsupport.co`
- URL: `https://m1crosoftsupport.co/login`
- IP destination of the URL: `45.148.10.131`

### Investigation & Analysis
`c.allen@thetrydaily.thm` received an email from `no-reply@m1crosoftsupport.co` containing a suspicious URL: `https://m1crosoftsupport.co/login`, and the sender’s email address appeared suspicious. This activity occurred at 09/17/2026 03:50. The user `c.allen@thetrydaily.thm` is associated with the IP address: `10.20.2.25` and Host: `win-3463`.

The URL has been analyzed and determined to be MALICIOUS by TryDetectThis.<br>
<img width="653" height="276" alt="Screenshot 2026-09-17 095734" src="https://github.com/user-attachments/assets/6722b1ab-9da4-4554-8d8e-392263e63c11" />

**(Correlated Event Found)**

After analyzing the SIEM logs for other events related to the same user and URL, a firewall event was found a few minutes after the email was received.<br>
<img width="404" height="221" alt="Screenshot 2026-09-17 100659" src="https://github.com/user-attachments/assets/c65088b5-6c47-424a-bf5f-a929a3c97d66" />

The firewall detected that the source IP `10.20.2.25` associated with the email recipient, attempted to access that URL. The URL pointed to an unknown IP address :`45.148.10.131`, and this correlated event occurred at 09/17/2026 03:51.

An analysis of the destination IP using TryDetectThis returned a MALICIOUS status.<br>
<img width="653" height="273" alt="Screenshot 2026-09-17 100744" src="https://github.com/user-attachments/assets/2d627475-9819-4e00-8fc6-66ae90828d9d" />

This activity indicates a phishing attempt and a spoofed email domain. No further suspicious activity was identified in the available telemetry.

### Classification & Escalation
| Classification      | Escalation                      |
|---------------------|---------------------------------|
| True Positive (TP)  | Further investigation required  |

### Final Assessment
The alert is classified as a True Positive. Based on the analysis, it can be concluded that the user and the internal IP address received a phishing email sent from a spoofed Microsoft domain, and the firewall detected that the user attempted to access the destination URL and IP address, which were flagged as MALICIOUS.

Since the user accessed a malicious URL and the firewall allowed the connection, escalation is essential to determine whether any payload, malicious content, or further activity reached the endpoint.

### Remediation Recommendation
- Monitor the affected user and endpoint
- Review endpoint activity after URL access
- Block the malicious URL and IP address
- Isolate the endpoint if compromise is confirmed
- Update email and web security controls
- Provide phishing awareness training to the user
