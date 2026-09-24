## Project 01 - Alert Investigation

### Objectives
- Analyze affected entities and attack indicators
- Determine whether an alert is classified as a True Positive or a False Positive
- Correlate related events when applicable
- Document investigation findings
- Assess whether escalation is necessary
- Explain the rationale behind classification and escalation decisions
- Provide appropriate recommendations for remediation

### Skills Demonstrated
- Alert Investigation
- Alert Classification
- IOC Identification
- Analysis of evidence such as IP Addresses, Email, URLs, Threats, and Logs
- Event Correlation
- Security Documentation

### Environment & Tools
This project uses the Cloud-Based SOC Simulator: “Introduction to Phishing” provided by TryHackMe to analyze, investigate, classify, and write security alert reports.

| Tools / Components    | Purpose                                                                                                               |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------|
| **Documentations**  | Provides guidance on alert triage, classification, and reporting, as well as information about employees such as email addresses, hosts, and IP addresses and the corporate network.  |
| **Dashboard**       | Displays security alerts and provides initial information and context for each alert.                                   |
| **TryDetectThis**   | Designed to analyze indicators such as URLs and IP addresses and assess the reputation of those indicators.             |
| **Splunk Log**            | Provides security logs related to investigated alerts for further analysis and investigation.                     |

### Cases
| Alert Case | Severity | Verdict| Investigation Focus                                                                                                 |
|-----------------|----------|------|------------------------------------------------------------------------------------------------------------------|
| [Case 01 - Legitimate Employee Onboarding Email](./Case-01-Legitimate-Employee-Onboarding-Email.md)      | Medium | FP | Benign Email                |
| [Case 02 - URL Shortening Sent by a Suspicious Sender](./Case-02-URL-Shortening-Suspicious-Sender.md)    | Medium | TP | Suspicious URL              |
| [Case 03 - Blacklisted External URL Blocked by Firewall](./Case-03-Blacklisted-External-URL-Firewall.md) | High   | TP | Suspicious Network Activity |
| [Case 04 - Spoofed Domain Sending Suspicious URL](./Case-04-Spoofed-Domain-Suspicious-URL.md)            | Medium | TP | Spoofed Domain with Suspicious URL & Event Correlation |
