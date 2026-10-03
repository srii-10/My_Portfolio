## SIEM Investigation Report

### Alert Information
- Alert: `Suspicious Process`
- Affected Host: `HR_02`
- Affected User: `Chris`
- Process: `cudominer.exe`
- Timestamp: `06/05/2022 12:40 AM (PKT)`

### Investigation & Analysis
The investigation begins by monitoring the SIEM dashboard and identifying alerts related to suspicious process. These process are then examined to identify the affected host and user, process information, and timestamp associated with the alert. <br>
<img width="529" height="406" alt="1" src="https://github.com/user-attachments/assets/6401dba9-ca9c-4882-902b-4b6e8165dddc" />
<img width="528" height="150" alt="3" src="https://github.com/user-attachments/assets/61682df5-f8ef-412f-8363-44e3900db8e8" />

Available event logs are reviewed to identify events that match the alert information. Relevant event are correlated based on the process name appearing on the dashboard page. Event log matching the alert (red line) are then identified. <br>
<img width="529" height="376" alt="4" src="https://github.com/user-attachments/assets/b9f8a058-9b7b-4a88-9a69-8df0ac124053" />

The associated detection rule is then examined to understand the conditions that triggered the alert. The suspicious process alert was triggered by one of the process names, `“miner”` (red line). <br>
<img width="529" height="203" alt="5" src="https://github.com/user-attachments/assets/87a8ba0e-2d4f-466d-be84-79f6434a8537" />

### Classification & Response
| Classification     | Response     |
|--------------------|--------------|
| True Positive (TP) | Isolate Host |

### Final Assessment
...
Aktivitas yang diamati sesuai dengan kondisi yang ditetapkan oleh aturan deteksi. Berdasarkan bukti yang tersedia, peringatan tersebut dianggap mencurigakan dan memerlukan tindakan lebih lanjut, bukan sekadar dianggap sebagai false positive.
