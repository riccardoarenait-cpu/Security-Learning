# Web attacks 

Web applications are one of the most common attack surfaces, because they're publically accessible and handle sensitive data

### Client side attacks

They abuse weaknesses in user behavior or browsers

A successful attack can result in data loss

Usually out of SOC visibility because they happen on the user's system

Examples : XSS, CSRF

--------

### Server side attacks

Exploiting vulnerabilities in web servers : server logic, misconfigurations

They leave evidence within SOC visibility

Examples : SQLi, Brute force

**SIMULATION** 

in this simulation I used Wireshark to analyse PCAP files and find the password discovered by the attacker and the information retrieved from a database

<img width="1687" height="823" alt="image" src="https://github.com/user-attachments/assets/d6bd59b8-d563-4606-b514-8b12f2824186" />

-------

## Key Takeaways

- Web attacks can target either the client or the server.
- Client-side attacks exploit user browsers and behavior.
- Server-side attacks target application logic, databases, and configurations.
- Network captures can provide valuable evidence during investigations.
- Wireshark can be used to reconstruct attacker actions and identify compromised data.

