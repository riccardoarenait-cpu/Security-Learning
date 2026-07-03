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

------------

## C2

a process that connects back to the attackers and waits for their commands 24/7

<img width="1415" height="637" alt="image" src="https://github.com/user-attachments/assets/afaf3b8e-1e6b-4cb3-bd42-7553494362da" />

in this screenshot I analyzed sysmon logs detecting c2 traffic

--------

## Persistence

Maintaining access for a long period of time

Example if accessed via RDP : creating backdoor or shell, create a new user as admin

trackable by security event 4720 (account creation), 4732 (user added to group), 4724 (password reset)

if accessed via Phishing : they have to install a malware

Methods : 

- Create windows service = sc create "BadService" binpath= "C:\malware.exe" start= auto \\ IDs 1 and 4697 service creation

- Create scheduled task = schtasks /create /tn "BadTask" /tr "C:\malware.exe" /sc onstart /ru System \\ IDs 1 and 4698 scheduled task creation

<img width="1533" height="879" alt="image" src="https://github.com/user-attachments/assets/c061ecfa-4d2b-4253-aba5-6cbea885b2e9" />

in this screenshot I investigated persistence using Sysmon

----------------

