if a service is listening = open port

filtered = nmap can't determine if open or close, but it's accessible

TCP header flags:

URG : incoming data is urgent

ACK

PSH : push flag

RST : reset the connection

SYN

FIN : no more data to send

----------------------------------

**Commands learned**

nmap -sT 10.112.178.178 (discover TCP open ports)

nmap -sS 10.10.105.229 (TCP SYN scan)

--------------------------------

UDP scan = if port is open, no reply, if closed, ICMP port unreacable error

------------------------------

**SIMULATION**

In this simulation I tried some of the commands learned and answered the questions
<img width="835" height="913" alt="image" src="https://github.com/user-attachments/assets/d8bd1401-ead0-496f-977e-aec9d3d167ca" />
