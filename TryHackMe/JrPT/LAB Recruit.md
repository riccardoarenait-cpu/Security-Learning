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

The credentials are stored in config.php, but there's no way to open it directly because the website treats it as script

we can open it using the  protocol wrapper file:// to bypass filters and view the content

<img width="757" height="652" alt="image" src="https://github.com/user-attachments/assets/65945f6a-23ce-491d-ad42-5646ff933025" />

here we can see the username is going to be Hr and the password hrpassword123

<img width="1396" height="573" alt="image" src="https://github.com/user-attachments/assets/3a21e8d4-2f5d-42c6-b736-d4c7a3c476a6" />

The 'search candidate name' query is actually vulnerable to SQL injection, this is discoverable by putting ' as an input and receiving an SQL 

error as a response.

The first step is guessing the number of columns using union select, only 1,2,3,4 doesn't return errors

<img width="1361" height="497" alt="image" src="https://github.com/user-attachments/assets/d390cf06-41cb-4a14-8d70-808ae4458965" />

Now we ask for the table name using information_schema.tables

<img width="1372" height="534" alt="image" src="https://github.com/user-attachments/assets/daadcc2e-cdd9-4751-8842-62cc64df5e93" />

The two possible tables are candidates and users, now we'll use information_schema.columns to look at the columns inside users

<img width="1357" height="608" alt="image" src="https://github.com/user-attachments/assets/5bbbd98a-8938-4a22-a190-043417dde8d7" />

Now we look at the columns id, username and password to find admin credentials

<img width="1319" height="499" alt="image" src="https://github.com/user-attachments/assets/7ca2cb7a-6534-4f1b-afbe-b894e506fa3a" />

Now we just have to insert the credentials in the login page

<img width="1330" height="480" alt="image" src="https://github.com/user-attachments/assets/901ecd54-9353-458c-b373-d1687d4a452a" />









