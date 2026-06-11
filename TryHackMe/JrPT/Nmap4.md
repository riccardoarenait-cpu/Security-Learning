# Identify the service 


adding -sV will visualize the service and version running on the port, it will force TCP connection

Nmap can also tell the operating system by adding -O

Saving results of nmap scan :

1 Normal : nmap -oN scan.nmap 10.113.177.95 (file name)

2 Grepable : -oG FILENAME

3 XML : -oX FILENAME

----------------------

**Commands learned** 

sudo nmap -sV --version-light 10.201.118.127

sudo nmap -sS -O 10.113.177.95

nmap -sS --traceroute 10.201.118.127

nmap -sC -p 80 10.113.177.95 (execute scripts)

-----------------------------------

**SIMULATION**

in this simulation I tried the commands learned against a virtual machine

<img width="1273" height="945" alt="image" src="https://github.com/user-attachments/assets/e5b29e43-b761-472d-b342-b30c3c448d0f" />
