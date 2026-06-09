Network mapper: standard tool for mapping networks, indentifying live hosts, discovering running services

steps of nmap scan:

1 Enumerate

2 Discover live hosts

3 Reverse DNS lookups

4 Scan ports

5 Detect versions

6 Detect OS

7 Traceroute

8 scripts

9 write outputs

-----------------------------------

**comands**

list: MACHINE_IP scanme.nmap.org example.com || nmap -iL list_of_hosts.txt

range: 10.11.12.15-20

subnet: MACHINE_IP/30

nmap -sn targets

sudo nmap -PR -sn 10.200.6.0/24 (ARP scan)

sudo nmap -PE -sn 10.200.6.0/24 (ping)

nmap -PP -sn 10.200.6.0/24 (timestamp)

nmap -PM -sn 10.200.6.0/24 (mask)

nmap -PS -sn 10.200.6.0/24 (TCP syn)

sudo nmap -PA -sn 10.200.6.0/24 (ACK)

sudo nmap -PU -sn 10.200.6.0/24 (UDP ping)
---------------------------------

priviledged user + local network = ARP requests

priviledged user + outside network = ICMP requests, TCP ack 80, TCP syn 443

unpriviledged user + outside network = TCP handshake, syn 80 443

ARP scan = discover live hosts

--------------------------------

reverse DNS = resolving an ip address to a hostname

-R forces, -n disables

-sn host discovery only
