# Linux priviledge escalation

Priviledge escalation : going from a lower to a higher permission account 

### Enumeration 

OS Commands : 

- uname -a = system information

- cat /proc/version = view the target system processes

- ps = see running processes

- cron service =  /etc/crontab , /var/spool/cron/ , /etc/cron.d/

User commands :

- id = user's priviledge level and group

- env = environmental variables

- cat /etc/passwd = discovers users

  <img width="1864" height="896" alt="image" src="https://github.com/user-attachments/assets/8fb7ecef-feb0-4e72-be4d-dabc4019d6d8" />

in this screeenshot I tried the commands listed above

Network commands :

- ifconfig = network interfaces

- netstat = gathers informations on existing connections

<img width="875" height="544" alt="image" src="https://github.com/user-attachments/assets/f4e8b338-7151-406a-906b-1ad0cc129984" />
  
in this screeenshot I tried the commands listed above

-----------

PATH: environmental variable, directories can be located under PATH

Capabilities: Method use for giving users higher privilegdes temporary

Cron jobs: Scheduled scripts and tasks

-------

Automating enumeration :

- LinPeas = automated script that spots priviledge escalation vulnerabilities

- LinEnum = Reports all system info, cron, SUID, users

- LES = Matches the kernel version against known CVEs
















