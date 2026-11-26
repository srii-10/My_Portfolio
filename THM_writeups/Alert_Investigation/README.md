## Project 01 - Alert Investigation

### Objectives
- Analyze affected entities and attack indicators
- Determine whether an alert should be classified as True Positive or False Positive
- Assess whether escalation is necessary
- Explain the rationale behind classification and escalation decisions
- Provide appropriate recommendations for remediation

### Environment & Tools
This project uses the Cloud-Based SOC Simulator: “Introduction to Phishing” provided by TryHackMe to analyze, investigate, classify, and write security alert reports.

| Tools / Components    | Purpose                                                                                                               |
| ------------------- | --------------------------------------------------------------------------------------------------------------------- |
| **Documentations**  | Provides guidance on alert triage, classification, and reporting, as well as information about employees such as email addresses, hosts, and IP addresses and the corporate network.  |
| **Dashboard**       | Displays security alerts and provides initial information and context for each alert.                                 |
| **TryDetectThis**   | Used to analyze indicators such as URLs and IP addresses and assess the reputation of those indicators.               |
| **SIEM**            | Provides security logs related to investigated alerts for further analysis and investigation.                         |

### Skills
- Evidence Analysis
- IOC Analysis
- Alert Triage
- Alert Classification
- Alert Reporting
- Alert Escalation

### Cases
| Alert Case | Severity | Type | Verdict|
|-----------------|----------|------|--------|
| [Case 01 - Legitimate Employee Onboarding Email](./Case-01-Legitimate-Employee-Onboarding-Email.md)      | Medium | Phishing | FP |
| [Case 02 - URL Shortening Sent by a Suspicious Sender](./Case-02-URL-Shortening-Suspicious-Sender.md)    | Medium | Phishing | TP |
| [Case 03 - Blacklisted External URL Blocked by Firewall](./Case-03-Blacklisted-External-URL-Firewall.md) | High   | Firewall | TP |
| [Case 04 - Spoofed Domain Sending Suspicious URL](./Case-04-Spoofed-Domain-Suspicious-URL.md)            | Medium | Phishing | TP |
