# Support 

A new internal Support Operations Platform has been deployed to assist IT and helpdesk teams. The application handles user management, internal APIs, and system-level operations. However, security was not the primary focus during development. Several features rely on user-controlled input and weak trust boundaries.

Can you pentest the platform and escalate your access to achieve RCE on the server?

Goals : access the platform as admin, discover content of the file /home/ubuntu/user.txt


------------

## Quest 1

First step : view the page source to find how the platform handles credentials

<img width="831" height="165" alt="image" src="https://github.com/user-attachments/assets/752e68bc-d2cd-4934-9800-42c365992cc9" />

Since the email is the same for everybody, we can perform a brute force attack on common passwords

hydra -l help@support.thm -P /usr/share/wordlists/rockyou.txt 10.112.136.134 http-post-form "/index.php:email=^USER^&password=^PASS^:Invalid credentials" -V -f

<img width="1211" height="674" alt="image" src="https://github.com/user-attachments/assets/d08a6180-595a-4608-b4f3-beab38a2e8e1" />

We managed to enter the dashboard with the credentials retrieved

<img width="1682" height="431" alt="image" src="https://github.com/user-attachments/assets/bb5c7964-e11e-4ec4-92a0-f54318dd060c" />

Upon analyzing the request with Burp Suite repeater, we see that one cookie string is randomized and the other isITUser is set by the developers, in particular it's an MD5 hash that means false when reversed looked up

<img width="1429" height="643" alt="image" src="https://github.com/user-attachments/assets/4100d85f-49b0-4967-82ee-c5bb795bb46b" />

After setting the hash as true, the response we get is from the admin panel

<img width="1416" height="694" alt="image" src="https://github.com/user-attachments/assets/84b147fd-b891-4c12-86fe-abc3d78aab01" />

Now we have to change the cookies with the developer's tool and we'll view the admin panel

<img width="1308" height="695" alt="image" src="https://github.com/user-attachments/assets/251ea42e-390b-4472-aa2c-9d03d8890b6b" />

We can access the api.php directory and see how the API request and response are structured

<img width="1316" height="623" alt="image" src="https://github.com/user-attachments/assets/60dc4020-84de-4c7f-bf97-8a478650f924" />

If we select user/1, we find the admin's account

<img width="546" height="270" alt="image" src="https://github.com/user-attachments/assets/70eea15c-d6a1-462a-9119-eb211c2feaf5" />

If we try to change skin color of the dashboard page and travel back the directories to open the config.php file, we can find a password in the page source

<img width="1023" height="507" alt="image" src="https://github.com/user-attachments/assets/afbc1f2e-36c8-473c-b500-a60cbeab470f" />

Using that password in combination with the email found earlier we can access as admin

<img width="1732" height="617" alt="image" src="https://github.com/user-attachments/assets/92d7820d-b554-4c27-a7d0-a427d5eb6fba" />

-------------

## Quest 2

If we load the dashboar after the login as administrator, we can see a new interface is present that sends a request to capture the current date or the current time

<img width="1754" height="773" alt="image" src="https://github.com/user-attachments/assets/604c8698-27f6-4e9b-9e93-3e02a299e331" />

We can now edit and resend the request to access the content we're looking for

<img width="1899" height="785" alt="image" src="https://github.com/user-attachments/assets/5889331c-12c6-4255-8ecb-7ca39234274c" />

After putting our injected code into the application the file is visible and the exercise is concluded

<img width="1897" height="801" alt="image" src="https://github.com/user-attachments/assets/55f695f4-65ad-4588-9a06-8a764489517a" />



