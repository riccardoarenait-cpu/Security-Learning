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

-----------

### Port scan

search portscan = commad that lists the port scan modules

auxiliary/scanner/portscan/tcp = most common module

use = command to use a module 

nmap can also run on metasploit

the auxiliary module can also perform service specific scans

example : auxiliary/scanner/netbios/nbname, auxiliary/scanner/http/http_version 

<img width="1630" height="806" alt="image" src="https://github.com/user-attachments/assets/b18c1004-910c-4016-88c1-8c5ef1663657" />

In this screenshot I ussed the auxiliary module to find the password associated with the username "penny"

db_nmap = nmap but stores everything in a database

host = command that lists every host the database knows about

services = command that lists every open port and the associated service

creds = command that lists credentials collected

-----------

### Meterpreter

Advanced multi function payload that runs in a target system as agent is a c2 architecture

it runs entirely in the target's RAM

all traffic between it and your machine is encrypted

multiple capabilities can be added with the load command

Windows meterpreter is the original, it uses DLL injection

Mettle is the cross platform counterpart

others are Java/PHP/Python meterpreter

Meterpreter commands :

- sysinfo = displays information about the target

- getuid = shows the user account meterpreter is running as

- getpid = returns the process ID

- ps = lists running processes on the target

- pwd,cd,ls = navigate directories

- cat, search, download, upload...

- ifconfig, netstat = network configurations

Migration = moving your meterpreter session from one process to another

-------------

### Msfvenom

Msfvenom is a command line tool that generates payloads for any target platform

you can generate executables, create web shells, encode and inject payloads

A basic msfvenom command has the payload, the format and the connection parameters

msfvenom -p <payload> LHOST=<your_ip> LPORT=<your_port> -f <format> -o <output_file>

-l = lists available payloads, example: msfvenom -l payloads | grep linux | grep meterpreter

Executable formats : produce binary files that the target OS can run directly (exe, elf, apk, war)

Transform formats : produce code that you embed into another tool (raw, c, powershell, python, base64)










