# Elastic alert triage

In this room I practiced scenarios where I had to detect malicious activity using Elastic

### Web attacks

<img width="1912" height="910" alt="image" src="https://github.com/user-attachments/assets/fe7a798f-65ad-4dd3-ad3b-281a4b88a4d0" />

In this screenshot I used Elastic to investigate a high severity suspicious web request that can indicate web shell activity

GET requests were made to a ASPX file with query parameters, using cmd=

-------------

### Account activity

In this scenario I used Elastic to investigate critical alerts of Administrator login outside business hours and an account creation using that

<img width="1902" height="912" alt="image" src="https://github.com/user-attachments/assets/4864ab36-2296-4e88-99fd-10b38d745f00" />

<img width="1906" height="902" alt="image" src="https://github.com/user-attachments/assets/a18f1493-e7cd-460b-a63f-68648b687bfe" />

----------------

### Command execution

In this scenario I used Elastic to investigate a critical alert regarding priviledge change behavior, done by the attacker via CLI

<img width="1907" height="906" alt="image" src="https://github.com/user-attachments/assets/ec88f6fa-07ce-47c9-88e7-68a54d46a1f3" />

In this screenshot we can see the attacker adding himself to a group using the net command

-------------------
