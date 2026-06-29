Unauthorized transfer of data from an organization to an external destination by an adversary

for financial gain, espionage, ransomware, sabotage, persistence

Common phases for exfil :

Discovery : attacker discovers the files

Compression : attacker aggregates files

Transport : transfer over the network

C2 coordination : orchestrates transfer and confirms receipt

-----------------

**Techniques**

Network based = HTTP uploads to cloud, DNS tunneling, cover protocols

indicators = Proxy, firewall, NGFW flow, DNS logs

Host based = Powershell, web request, USBs

indicators = EDR, windows security, linux shell history

Cloud exfil = S3, Azure uploads, external sharing

indicators = CloudTrail, Azure activity, access logs

-------------------

DNS tunneling :

usually allowed from hosts, it looks like normal requests, data is encoded into DNS queries

indicators : many queries sent to the same domain at regular intervals, high entropy and long subdomains, no reponse

<img width="1521" height="835" alt="image" src="https://github.com/user-attachments/assets/636db2b5-7a25-49e1-b58a-f6d30dcedf86" />

----------------

FTP : attackers use FTP to move files and data over a network, through legitimate FTP servers, compromised credentials, non standard ports

indicators : USER and PASS commands, STOR (upload) and RETR (download), large connections to unusual IPs

wireshark filters = ftp.request.command == "USER" || ftp.request.command == "PASS"

ftp contains "STOR" , ftp && frame.len > 90

<img width="1534" height="800" alt="image" src="https://github.com/user-attachments/assets/d28fa03f-3dba-44a5-9446-95328fbaab22" />

---------------

HTTP : attaker moves sensitive data out of a network using HTTP

very common, looks legitimate

means : POST uploads, GET requests, custom headers, TLS tunneling

indicators : requests to unusual domains, large, frequent

wireshark filters : http.request.method == "POST" and frame.len > 500

<img width="1317" height="510" alt="image" src="https://github.com/user-attachments/assets/41d7a84e-fe4d-4580-9e8b-3dc0bf3c2dad" />

-----------------

ICMP : echo and reply functions, encoded files into payloads, persistent, large

wireshark filters : icmp.type == 8 and frame.len > 100

<img width="1810" height="755" alt="image" src="https://github.com/user-attachments/assets/a2f631c3-709d-4567-a2fb-59616410f891" />
