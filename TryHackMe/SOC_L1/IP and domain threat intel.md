# IP and domain threat intel

### Resolving domains

Resolving a domain by using tools like whois lookups can tell a lot of information about a suspicious domain, including records, IP addresses, tools used

Types of DNS attacks :

- CDN abuse = An attacker uses a CDN to hide his malicious activity

- Typosquatting = using visual similarities or relying on user error in typing the domain to redirect to a malicious website

- IDN attacks = using non ASCII characters from another alphabet to look the same as latin


<img width="794" height="919" alt="image" src="https://github.com/user-attachments/assets/e30525f7-4996-457a-89a4-c57ea8910c55" />

In this screenshot I used a whois lookup to gather information about a domain

--------------------------

### IP enrichment

Most alerts come with an IP address, there are tools that help the analyst understand the origin of the IP

- Virustotal = Reputation, comments, details

- AbuseIPDB = reporting IPs and reputation check

- ipinfo = geolocation, organization

<img width="1651" height="946" alt="image" src="https://github.com/user-attachments/assets/037cfc7c-d950-48aa-96ca-56846d774795" />

------------

### Service exposure

Knowing what services are exposed is useful for both the attacker and defender, there are multiple tools to discover details about open ports

- Shodan = searches for internet connected devices, shows details about open ports

- Censys = Shows exposed services and offers advanced research capabilities

<img width="1899" height="948" alt="image" src="https://github.com/user-attachments/assets/1fe79d4c-9683-449d-a0b4-751a3429a251" />

In this screenshot I used Censys to learn about the exposed services related to a host

--------------


