# MITM detection

##an attacker secretely intercepts and alters communication between two parties

Common types : packet sniffing, session highjacking, SSL stripping, DNS spoofing, IP spoofing

an attacker manipulates protocols to intercept a comunication channel

--------------

ARP spoofing

attacker sends fake ARP requests to trick devices into associating their MAC address to  legitimate IP

indicators : multiple MAC same IP, Replies without requests, abnormal traffic

wireshark filters : arp.isgratuitous (unsolicited replies)

<img width="1077" height="557" alt="image" src="https://github.com/user-attachments/assets/5d67855f-224b-44e8-ac8d-454b1adb4a2d" />

------------------

DNS spoofing

attacker provides his IP in a DNS response

indicators : multiple DNS responses, response from unexpected source, short TTL, unsolicited response

wireshark filters : dns.flags.response == 1 && ip.src != 8.8.8.8 (search for IPs that aren't common DNS servers)

<img width="1657" height="769" alt="image" src="https://github.com/user-attachments/assets/313b999e-e508-4c0a-9ff8-1f7fab1d43b2" />

-----------------

SSL stripping 

phases : 

- victim initiates an HTTPS request to a website

- the attacker intercepts the request

- the attacker connects to the website using HTTPS but sends the response to the victim with HTTP

- the victim continues iteracting with HTTP

indicators : the initial request was HTTPS but it shifted to HTTP, certificate errors

<img width="1157" height="595" alt="image" src="https://github.com/user-attachments/assets/5e41c9e8-7035-4e60-892d-6beb29783d87" />
