## Scenario 01 - Malicious PS Download

### Scenario Information
<img width="562" height="118" alt="NTAB" src="https://github.com/user-attachments/assets/217d8e4f-29ce-4f03-a00e-37d3b97bf5da" /> <br>

**List of related entities:** <br>
- IP User: `192.168.0.3`
- IP Indicator: `203.0.113.200`
- Suspicious Domain: `www.tryhackrne.thn`
- Path File: `/downloads/install.ps1` <br>

Below is a network topology diagram for a company, and the “Drop here” label is provided to indicate where to place the TAP according to the diagram so that Web traffic can be captured for investigation. <br>
<img width="496" height="350" alt="Screenshot 2026-09-25 151155" src="https://github.com/user-attachments/assets/3b10b626-4873-4a23-9029-3730d1760952" />

### Investigation & Analysis
**1. TAP Placement** <br>
Based on this scenario, the TAP must be placed after WP1 (Web Proxy). Once the TAP has been properly deployed (as shown in the green notification block), it will capture all Web traffic entering and leaving the network. Specifically, it will identify HTTP method packets. <br>
<img width="549" height="258" alt="Screenshot 2026-09-25 151213" src="https://github.com/user-attachments/assets/3e3ffa55-d85f-479d-bc55-d6a76583775d" />

**2. HTTP request packet** <br>
At 29/09/2025, an HTTP request packet from IP address `192.168.0.3` was detected in Web traffic containing a download request (curl) for a suspicious file named `install.ps1`, directed at the suspicious host/domain `www.tryhackrne.thn` via `port 80`. That host/domain is associated with the unknown IP address `203.0.113.200`. <br>
<img width="544" height="410" alt="Screenshot 2026-09-25 151429" src="https://github.com/user-attachments/assets/7d2686a1-7135-437d-b00c-4c2a96f69847" />

**3. HTTP response packet** <br>
After the HTTP request packet was analyzed, the web traffic was re-examined to find related packets. An HTTP response packet was found that contained relevant indicators, with the HTTP response returned a `200 OK` status and used HTTP/1.1 over an unencrypted HTTP connection. This allows the transmitted content to be observed during network traffic inspection. <br>
<img width="544" height="410" alt="Screenshot 2026-09-25 151547" src="https://github.com/user-attachments/assets/0c18b27b-db76-47c5-9a0f-17272cf28a17" />

**4. Indicator Identification** <br>
A PowerShell script indicator was also found in the Body Preview as the FLAG that had to be found in that packet as the answer to a question in that THM room. <br>
<img width="546" height="202" alt="Screenshot 2026-09-25 151619" src="https://github.com/user-attachments/assets/9badf40d-ef54-4025-9af2-585d2a4ea3fe" />

### Investigation Findings
The investigation identified suspicious HTTP traffic originating from workstation `192.168.0.3` following the user's interaction with the phishing link. The HTTP request targeted the suspicious domain `www.tryhackrne.thn` and requested the file `/downloads/install.ps1` from IP address `203.0.113.200`. <br>

The associated HTTP response contained a PowerShell script indicator in the response body, confirming that the traffic involved the download of a PowerShell script. The identified IP address, domain, requested file, and PowerShell content should be treated as relevant indicators for further investigation.

### Remediation Recommendations
- Block malicious IP/domain
- Conduct an in-depth investigation to determine whether there are any other related activities
- Isolate the workstation if it has been compromised
- Search for the identified indicators across other potentially affected hosts
- Provide awareness training to users regarding suspicious domains and links
