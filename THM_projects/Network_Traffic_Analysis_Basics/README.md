## Project 02 - Network Traffic Analysis Basics

### Objectives
**Learning Objectives**
- Know what network traffic analysis is
- Know what can be observed
- Know how to observe network traffic
- Know typical network traffic sources and flows

**Practical Objectives**
- Determine appropriate network TAP placement for capturing Web and DNS traffic
- Identify potentially malicious packets within Web and DNS traffic
- Analyze suspicious Web and DNS packets to identify indicators
- Extract flags from the identified malicious packets

### Skills Demonstrated
- Network Traffic Inspection
- Suspicious Packet Identification
- Indicator Identification
- Packet Content Analysis
- Evidence Analysis

### Environment & Tools
This project uses the “Network Traffic Basics” lab provided by TryHackMe to analyze, investigate, and find flags in malicious traffic.

| Tools / Components                | Purpose                                                                         |
| ----------------------------------|---------------------------------------------------------------------------------|
| **Traffic Analysis Lab**          | Provides information about incidents, devices, and Web and DNS traffic packets. |
| **Device Description**            | Provides a description for each device.                                         |
| **Incident Context**              | Brief information about an incident.                                            |
| **Packets**                       | Provides Web and DNS traffic packets.                                           |
| **Network Environment Structure** | An overview of a network’s structure and provision of space for TAP.            |

### Scenarios
| Scenario Name                                                                 | Investigation Focus    |
|-------------------------------------------------------------------------------|------------------------|
| [Scenario 01 - Malicious PS Download](./Scenario-01-Malicious-PS-Download.md) | Investigating HTTP traffic associated with a phishing link and malicious PowerShell file download. |
| [Scenario 02 - DNS Infiltration](./Scenario-02-DNS-Infiltration.md)           | Investigating suspicious DNS TXT records used to deliver malicious C2 instructions. |
