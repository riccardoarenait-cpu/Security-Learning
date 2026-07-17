# Splunk alert triage

In this room I practised against different scenarios of security breaches, using Splunk to analyse the attacker's behavior

### Initial access alert

For this scenario I used Linux logs

<img width="1882" height="855" alt="image" src="https://github.com/user-attachments/assets/103837e6-a543-4396-954a-c165b042b10f" />

In this screenhot I detected a brute force attempt against a specific user

<img width="1892" height="822" alt="image" src="https://github.com/user-attachments/assets/06a3ba6b-b10e-4a25-8b7a-cde239337f28" />

In this screenshot I discovered an account creation for persistence

------------

### Persistence alert

For this scenario I used Windows logs

<img width="1892" height="816" alt="image" src="https://github.com/user-attachments/assets/a3d84eef-35d6-4c5f-a4db-e2a31a605f7e" />

In this screenshot I used Splunk queries to discover the parent process that created a malicious task

------------


### Web shell alert

For this scenario I used web application logs

<img width="1892" height="820" alt="image" src="https://github.com/user-attachments/assets/3c818ae0-739c-4c8c-be65-3969559b0e14" />

In this screenshot I detected a we shell interaction using the file b374k.php

-----------------------

