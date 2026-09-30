## Scenario 02 - DNS Infiltration

### Scenario Information
<img width="565" height="100" alt="Screenshot 2026-09-25 151642" src="https://github.com/user-attachments/assets/3a2dbcf3-7d47-4dd6-856b-71f97781bb97" /> <br>

**List of related entities:** <br>
- Affected IP Addresses: `192.168.0.2`, `10.10.10.11`
- Malicious Domain: `c2.tryhackrne.thn`
- C2 Command: `THM{C2CommandFound}`<br>

Below is a network topology diagram for a company, and the “Drop here” label is provided to indicate where to place the TAP according to the diagram so that DNS traffic can be captured for investigation. <br>
<img width="496" height="350" alt="Screenshot 2026-09-25 151155" src="https://github.com/user-attachments/assets/3b10b626-4873-4a23-9029-3730d1760952" />

### Investigation & Analysis
**1. TAP Placement** <br>
Based on this scenario, most firewalls allow DNS (53) traffic to pass through without strict inspection. Therefore, a TAP must be placed after SW01 (Switch) on the path to the SRV-DNS (DNS Server) to capture all DNS traffic entering and leaving the network, including the contents of malicious packets. <br>
<img width="546" height="386" alt="Screenshot 2026-09-25 151716" src="https://github.com/user-attachments/assets/bb9bdc9f-3cec-4dca-a22c-b23c7e8a2e99" />

**2. DNS query packet** <br>
At 29/09/2025, a DNS request packet was detected in DNS traffic containing a TXT record request from the IP address `192.168.0.2` for the domain `c2.tryhackrne.thn` using the `UDP` protocol. <br>

In this scenario, malware that has infected the workstation by exploiting the DNS protocol is requesting a TXT record from that malicious domain. <br>
<img width="542" height="287" alt="Screenshot 2026-09-25 151941" src="https://github.com/user-attachments/assets/e2d6fd67-421a-4703-a9dd-305f8b4a6963" />

**3. DNS response packet** <br>
After the DNS request packet was analyzed, the DNS traffic was re-examined to identify related packets. A DNS response packet containing relevant indicators was found, the DNS response showed that the suspicious domain responded to the query with a “No error” status as if it were a legitimate request, and a malicious C2 command was found embedded in the TXT record (the answer FLAG from the question in the THM room). <br>
<img width="539" height="333" alt="Screenshot 2026-09-25 151954" src="https://github.com/user-attachments/assets/009fab16-4609-4cc6-a3be-83ab3b52354a" />

### Investigation Findings
The investigation identified malicious DNS traffic originating from the workstation `192.168.0.2` after it was confirmed that the workstation had been compromised. The DNS query showed a request for a TXT record from domain c2.tryhackrne.thn. <br>

The associated DNS response contained C2 command indicators, confirming that the traffic involved malicious C2 command requests to a suspicious domain. The identified IP address, unusual domain, and C2 commands should be treated as relevant indicators for further investigation and action.

### Remediation Recommendations
- Payload/command analysis
- Block C2 domains
- Isolate affected hosts and networks
- Continued monitoring
- In-depth investigation to identify other activities related to these indicators
- Implement Deep Packet Inspection (DPI) on TXT responses exhibiting suspicious signs
