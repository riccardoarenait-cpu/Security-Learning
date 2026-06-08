Endpoint Detection and Response = series of tools designed to protect endpoints
market solutions :
CrowdStrike Falcon
SentinelOne ActiveEDR
Microsoft Defender for Endpoint
OpenEDR
Symantec EDR

Key advantages = **Visibility**, **Detection**, **Response**

DIfference with AV's = AV's detect basic known threats, EDR provide surveillance and constant monitoring

Agents = singular endpoints equipped with EDR
EDR console = all the data (telemetry) collected from agents is analyzed via algorithms, detections happen here, dashboard gives all inforation

Telemetry collected by EDR : Process Executions and Terminations, Network Connections, Command Line Activity, Files and Folders Modifications, Registry Modifications

Detection : Behavioral Detection, Anomaly Detection, IOC matching, MITRE ATT&CK Mapping, Machine Learning Algorithms
Response : Isolate Host, Terminate Process, Quarantine, Remote Access, Artefacts Collection

![activity](<Screenshot 2026-06-07 210743.png>)