## SIEM Investigation Report

### Alert Information
- Alert: `Suspicious Process`
- Affected Host: `HR_02`
- Affected User: `Chris`
- Process: `cudominer.exe`
- Timestamp: `06/05/2022 12:40 AM (PKT)`

### Investigation & Analysis
The investigation begins by monitoring the SIEM dashboard and identifying alerts related to suspicious process. These process are then examined to identify the affected host and user, process information, and timestamp associated with the alert. <br>
<img width="529" height="319" alt="1" src="https://github.com/user-attachments/assets/773f0591-d3cc-421a-8ae9-23f6b233cf5d" />
<img width="528" height="150" alt="3" src="https://github.com/user-attachments/assets/61682df5-f8ef-412f-8363-44e3900db8e8" />

Available event logs are reviewed to identify events that match the alert information. Relevant event are correlated based on the process name appearing on the dashboard page. Event log matching the alert (red line) are then identified. <br>
<img width="529" height="376" alt="4" src="https://github.com/user-attachments/assets/b9f8a058-9b7b-4a88-9a69-8df0ac124053" />

The associated detection rule is then examined to understand the conditions that triggered the alert. The suspicious process alert was triggered by one of the process names, `“miner”` (red line). <br>
<img width="529" height="203" alt="5" src="https://github.com/user-attachments/assets/87a8ba0e-2d4f-466d-be84-79f6434a8537" />

The observed activity matched the conditions defined by the detection rule. Based on the available evidence, the alert was considered suspicious and required further response rather than being dismissed as a false positive.

### Classification & Response
| Classification     | Response         |
|--------------------|------------------|
| True Positive (TP) | Isolate the Host |

### Final Assessment
The investigation confirmed that the process alert was a **True Positive (TP)**.

The alert was supported by event correlated with the process name and detection rules that identified the suspicious activity. In response, **Isolate the Host** was selected to quarantine the affected endpoint and limit potential further activity. <br>
<img width="530" height="203" alt="6" src="https://github.com/user-attachments/assets/a5cc2e5e-2ac7-481e-908d-33b7fd02594b" />

The investigation was successfully completed after the alert was classified and the appropriate response action was selected. This is evidenced by the appearance of a FLAG at the end of the investigation (the response from the THM room). <br>
<img width="361" height="101" alt="7" src="https://github.com/user-attachments/assets/05188c12-3920-4929-a2a9-a768b5ccd8e2" />
