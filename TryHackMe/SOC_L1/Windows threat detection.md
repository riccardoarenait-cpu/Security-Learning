# Windows threat detection

Initial access is the start of every attack, threat actors can gain access through vulnerabilities, phishing, removable media

### RDP breach

Exposed vulnerable RDP is a big threat, it can lead to easy ransomware attacks

Attack stages : 

- Network scan = Botnet detects RDP exposed port

- RDP brute force = Botnet brute forces common usernames

- Initial access = the botnet guesses the correct password and enters

- Malicious actions = the threat actor logs in via RDP and reviews the desktop

How to detect :

- Step 2 = FIlter for failed logins (4625), logons type 3 and 10, from external IPs

- Step 3 = Filter for successful logins (4624), check the account

- Step 4 = Filter for logon type 10, interactive login, filter the logon ID to find processes started by the threat actor

------------

### Phishing detection

Double extensions = invoice.pdf.exe

malware with .com

LNK attachments :

They look legitimate, they have shortcuts pointing to powershell commands for example

have little execution trace

<img width="1898" height="853" alt="image" src="https://github.com/user-attachments/assets/8b0f0ac0-782c-4e14-a6b4-4aa96cf216ee" />

In this screenshot I used event viewer to track a successful phishing attack using LNK attachments

-------------

## Discovery

An attacker after gaining access needs to understand the environment and find tools to carry out the attack

Commands used : 

- Files and folders = type <file>, Get-Content <file>, dir <folder>

- Users and groups = whoami, net user, net localgroup, query user

- Systems and apps = tasklist /v, systeminfo, Get-Service

- Network settings = ipconfig /all, netstat -ano

<img width="1343" height="742" alt="image" src="https://github.com/user-attachments/assets/1aa36351-f40c-462c-9f91-f3dc4ed14e7d" />

In this screenshot I used sysmon to detect a net administrator command I just executed  

<img width="1274" height="744" alt="image" src="https://github.com/user-attachments/assets/f91173fc-4264-4d79-94d3-c503358c4988" />

in this screenshot I opened a malicious file on the VM and used sysmon to find out which commands it has executed










