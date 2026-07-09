# Cyber threat intel

Cyber threat intel provides the context that helps the SOC recognize what actvity is actually malicious

the job of a L1 analyst is to make artifacts useful and enrich them until they becoe intelligence, through indicators of compromise, indicators of attack, tactics, techniques and procedures

TLP Traffic Light Protocol governs how intel may be shared

- Clear : no restriction

- Green : share with related communities and SOCs

- Amber : share only within the company or need to know clients

- Red : share only with named recipients

  
### CTI lifecycle

- Planning and direction :

  brief planning meeting defining primary asset, business risk, available controls, initial goal

- Collection :

  gather information from sources like NGFW, MISP, reports, OSINT

- Processing :

  Normalising and collerating findings, applying tags, converting files

- Analysis :

  Figure out if the alerts are really malicious, if they come from multiple sources it should usually be an immediate block

- Dissemination :

  Deliver the intelligence to the teams of interest

- Feedback :

  Firewall and EDR reports show the progress of an efective threat intelligence flow

  








