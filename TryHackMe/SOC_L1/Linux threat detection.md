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







