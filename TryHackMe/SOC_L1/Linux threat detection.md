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





