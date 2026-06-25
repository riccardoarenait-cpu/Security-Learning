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
