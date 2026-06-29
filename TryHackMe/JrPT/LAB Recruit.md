Task : 

Recruit has just launched its new recruitment portal, allowing HR staff to manage candidate applications and administrators to oversee hiring decisions. While the platform appears functional, management suspects that security may have been overlooked during development. Your task is to assess the application like a real attacker, mapping its structure, abusing exposed functionality, and exploiting vulnerabilities.

Can you gain an initial foothold, escalate your access, and ultimately log in as the administrator?

<img width="867" height="476" alt="image" src="https://github.com/user-attachments/assets/64dc6634-de49-4509-b701-e4810e598b82" />

First step : Enumerate directories using gubuster, with common worldlists and extension search like .php .txt

<img width="989" height="682" alt="image" src="https://github.com/user-attachments/assets/ec83ac3c-9767-4208-a85c-f8082fdc1bb8" />


The directory of interest "mail", has been found, now navigate to the directory of interest in the browser

<img width="669" height="375" alt="image" src="https://github.com/user-attachments/assets/7b9086d7-f921-4715-9485-1864d0cf2516" />

in the file mail.log there are interesting informations about credentials

<img width="951" height="639" alt="image" src="https://github.com/user-attachments/assets/cc93b6ad-2a33-4cfa-9261-3cc4a765ade1" />
