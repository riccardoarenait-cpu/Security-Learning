# Linux logging

Linux logs are plaintext, easy readable but less structured, usually stored in /var/log

use grep for filtering

 /var/log/auth.log usually contains user management events, sudo commands, authetication events

 Commands to filter for auth.log events: 

-  cat /var/log/auth.log | grep -E 'session opened|session closed'

 -  cat /var/log/auth.log | grep "sshd" | grep -E 'Accepted|Failed'

 - cat /var/log/auth.log | grep -E '(passwd|useradd|usermod|userdel)\['

------------

Types of logs :

- /var/log/kern.log = kernel messages or errors

- /var/log/syslog = various events

- /var/log/dpkg.log = packet manager logs on Debian

- /var/log/dnf.log = packet manager on RHEL

  /.bash_history records every command you run

-----------

### Auditd

Auditd is a solution used by SOC for runtime monitoring

Ways of access : /var/log/audit/audit.log or ausearch command

Structure of an auditd log : 

- pid=3888, ppid=3752 = Process or parent process ID

- auid=ubuntu = The user for audit

- uid=root = the user who ran the command

- tty=pts1 = session identifier

- exe=/usr/bin/wget = path to the executed binary

-----------

<img width="860" height="445" alt="image" src="https://github.com/user-attachments/assets/0affb007-3ab0-4662-b6bc-6133fb441333" />

In this screenshot I tried some of the commands learned






