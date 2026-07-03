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

