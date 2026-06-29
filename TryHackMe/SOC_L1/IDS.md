# Intrusion detection system

Detects abnormal traffic and categorizes the threat

Types of deployment : 

- Host IDS = installed individually on the hosts

- Network IDS = detecting activity in the whole network

Detection modes :

- Signature based = attacks have their unique patterns called signatures, the IDS recognizes them

  pros : very efficient against known threats; cons : unable to detect zero day attacks

- Anomaly based = the IDS first learns the normal behavior, then detects deviations of that behavior

  pros : effective against zero day attacks; cons : a lot of false positives

- Hybrid = combines both methods, most effective

  --------------

  ## Real world IDS = SNORT

  Hybrid detection and can be configured to custom rules

  - packet sniffer mode = only reads and displays packets
 
  - packet logging mode = performs detection, displays alerts
 
  - NIDS mode = primary mode, monitors network traffic and applies its rules for detection
 
### Configuring IDS example 

we have to create a rule for the IDS to detect a loopback ping

let's start by editing the rule file : sudo nano /etc/snort/rules/local.rules

now we add the new rule : alert icmp any any -> 127.0.0.1 any (msg:"Loopback Ping Detected"; sid:10003; rev:1;)

now we set up the IDS to listen to the requests : sudo snort -q -l /var/log/snort -i lo -A alert_fast -c /etc/snort/snort.lua

now we try to ping on another terminal : ping 127.0.0.1

and the IDS will display the alerts just like in our rule

<img width="1032" height="237" alt="image" src="https://github.com/user-attachments/assets/5c2fc28b-c75f-4a57-a3c9-8a251a61efa0" />
