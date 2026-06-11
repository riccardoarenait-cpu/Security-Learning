Null scan = doesn't set any flag, if the port is closed, we receive a RST pack, either open or a firewall is blocking it

FIN scan = no response if the port is open

XMAS scan = // sends FIN, PSH, URG

Maimon scan = FIN and ACK sent, RST expected as a response

ACK scan = if a firewall is in front, you learn which ports weren't blocked by the firewall, useful to discover firewall rules

--scanflags RSTSYNFIN = custom scan

IP spoofing = nmap -S SPOOFED_IP 10.112.157.121 ;  the target will respond to the packets sending replies to the IP provided, the attaacker will capture replies to identify ports;

nmap -e NET_INTERFACE -Pn -S SPOOFED_IP 10.112.157.121

--spoof-mac SPOOFED_MAC if the attacker and target are on the same network

Decoys = the scan will appear to come from 3 different sources, the replies will go to the decoys too; nmap -D 10.10.0.1,10.10.0.2,ME 10.112.157.121 (ME = your address)

Fragmented packets = harder to raise a flag by IDS and firewall; -f

Zombie scan = requires an idle system connected to the network that you can communicate with, nmap will makes probes come from it; nmap -sI ZOMBIE_IP 10.112.157.121 

to get more details = --reason, -v -vv, -d -dd

--------------------------

**Commands learned** 

sudo nmap -sN 10.112.157.121

sudo nmap -sF 10.112.157.121

sudo nmap -sX 10.112.157.121

sudo nmap -sM 10.201.89.221

--------------------------------

**SIMULATION**

In this simulation I tried the new commands learned to discover open ports using nmap

<img width="1210" height="942" alt="image" src="https://github.com/user-attachments/assets/e6e89b6a-0578-4af6-99be-a8f280672824" />
