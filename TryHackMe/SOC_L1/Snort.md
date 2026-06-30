# Snort

Open source rule based NIDS/NIPS

capabilities : traffic analysis, attack detection, packet logging, protocol analysis, alerting

## IPS

Types : 

- NIPS = monitors traffic flowing through a network, protects the entire subnet, if signature is identified, connection is terminated

- NBA = Network behavior analysis, protects the entire subnet, if anomaly is detected the connection is terminated

- WIPS = Wireless IPS, monitors traffic from a wireless network

- HIPS = Monitors traffic from a single host

  ----------------------

  ## Interacting with Snort

  snort -V  (check if it's installed)

  sudo snort -c /etc/snort/snort.conf -T  (-T to test the connection, -c indentifies configuration file)

  ### Sniffer mode

  Parameters :

  -v Displays verbose TCP/IP output

  -d Displays packet data

  -e Displays link layer headers

  -X displays full packet details

  -i define specific interface to sniff

  <img width="1029" height="724" alt="image" src="https://github.com/user-attachments/assets/41a70d49-29c5-4076-b2fe-29c127cc5c26" />

  in this image I tried the verbose output option provided by Snort

  ### Packet logger

   Parameters :

  -l logger mode

  -K ASCII Log packets in ASCII format

  -r Reading option

  -n specify the number of packets to be processed

  ### IDS/IPS mode

  Parameters :

  -c Configuration file

  -T testing configuration file

  -N disable logging

  -D background mode

  -A alert mode, can be console, cmg, full, fast

  <img width="1280" height="728" alt="image" src="https://github.com/user-attachments/assets/f2c94bd6-65c4-4e82-955a-17da07689c61" />

   in this image I tried the console alert mode from Snort

  ### PCAP investigation

  Snort processes PCAP files an assigns alerts based on the ruleset

  Parameters :

  -r / --pcap-single=   (Reads single PCAP)

  --pcap-list=""   (Reads PCAPs provided)

  --pcap-show (Shows PCAP name)

-----------------

## Rule structure

  | Action | Protocol | Source IP | Source port | Direction | Dest IP | Dest port | Options |
|----------|----------|----------|----------|----------|----------|----------|----------|
| Alert, Drop, Reject | TCP, UDP, ICMP | Any |  Any | <> | Any | Any | msg, reference, Sid, Rev |

Example : alert icmp 192.168.1.56 any <> any any  (msg: "ICMP Packet From "; sid: 100001; rev:1

This rule will create an alert for each ICMP packet originating from the 192.168.1.56 IP address
