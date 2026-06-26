# Wireshark

one of the best network analyzer tool

troubleshoot networks, detect anomalies

<img width="1917" height="953" alt="image" src="https://github.com/user-attachments/assets/64c8d940-d5ae-4325-a3d8-6067c3680179" />

Packet dissaction = investigate packets by decoding available protocols and field

Packet detail

frame/packet : first layer of OSI

Source [MAC] : second layer of OSI, src and dest mac address

Source [IP] : third layer, ipv4

Protocol : layer 4, protocols used UDP/TCP

Application protocol : layer 5, HTTP,FTP,...


# statistics

Resolved addressed = identify ip addresses and DNS available in th capture file

Protocol Hierarchy = identify all ports in the capture file

Conversation = identify all conversations between endpoints

Endpoints = identify endpoints in detail

---------------------------

Commands query :

ip.addr ==

ip.src ==

ip.dst ==

tcp.port == 80

tcp.srcport == 1234

tcp.dstport == 80

http.response.code == 200

http.request.method == "GET" / "POST"

dns.flags.response == 0



<img width="1900" height="906" alt="image" src="https://github.com/user-attachments/assets/ff714c2b-ab92-41e4-a856-7a494a3d42c4" />


# Identify patterns

Nmap scans = tool for network mapping and live host discovery

The TCP three way handshake pattern is a good way to know if nmap is being used

UDP scans, only error when port is closed

ARP poofing = network manipuation by sending ARP packets and interfeering with IP to MAC table

indentifyable by looking if there are two different ARP responses

MITM attack = identifyable if the same MAc address is the destination of all communication

Filter : arp.duplicate-address-detected or arp.duplicate-address-frame

arp.opcode == 1 && eth.src == 00:0c:29:e2:18:b4

--------------

Host and user identification

DHCP traffic

Requests : dhcp.option.dhcp == 3

Accepted : dhcp.option.dhcp == 5

Denied : dhcp.option.dhcp == 6

NetBIOS traffic

allows applications on different hosts to communicate

Kerberos traffic 

secure authenticating service over untrusted network

ICMP tunneling = data exfiltration method and c2 connection

indicators : large volume of ICMP traffic, anomalous sizes  (data.len > 64 and icmp)

DNS tunneling : adversary creates a domain name and configures it as c2 channel, the malware sens DNS queries to c2, longer queries than usual, containing commands (dns.qry.name.len > 15 and !mdns)

