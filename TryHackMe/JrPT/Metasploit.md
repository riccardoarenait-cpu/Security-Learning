# Metasploit

Metasploit is an open source exploitation framework that contains libraries of exploits, scanners, payloads accessible through one interface

Metasploit supports the pentester's job : Information gathering, vulnerability identification, exploitation, post exploitation, reporting

Pillars of Metasploit framework: 

- Msfconsole : Command line iterface, where you can manage the framework

- Modules : Building blocks of metasploit, pieces of code designed to do specific tasks

- Tools : Other command line tools like Msfvenom

-------------

### Vulnerabilities, exploits, payloads

Vulnerability = a flaw in a target system that creates opportunity for harm

Exploit = a piece of code that takes advantage of a vulnerability

Payload = the code that runs of the system after the exploit succeeds

Seven categories of modules :

- Exploits = target a specific vulnerability on a specific platform

- Auxiliary = Handles everything that's not exploitation, port scans, brute force...

- Payloads = contains the code to execute on the target

- Post exploitation = runs after gaining access to a system

- Encoders = Transforms payload data into different formats

- NOP = intruction to skip an operation

- Evasion = bypasses security controls

Payload types :

- Singles = Self contained, delivered in a single package

- Stagers = small, only job is to extablish a communication channel

- Stages = Larger payloads downloaded by a stager

Exploit rakings : Excellent, great, good, normal, average, low, manual

-----------

### msfconsole

Commands :

Search type/plaform/cve/name : ...

info

help

Six important parameters : 

- RHOST = remote host, the target's IP address

- RPORT = Remote port, the port where the vulnerable service is running

- LHOST = Local host, your attacking IP address

- LPORT = Local port, the port on your machine that will receive connection

- PAYLOAD = the payload to deliver with the exploit

- SESSION = specifies which sessions the module should run through

The "set" commad assigns a parameter





  













