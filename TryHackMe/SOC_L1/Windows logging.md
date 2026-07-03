# Windows logging

The OS logs events processed, in windows they are stored in C:\Windows\System32\winevt\Logs under EVTX format

Event viewer is a tool for reading tose logs

-------

### Event ID types

4624 = successful login / 4625 = failed login

4720 = a user account was created / 4722 enabled / 4738 changed

4725 = an account was disabled / 4726 deleted

4723 = a user changed their password / 4724 a password was reset

4732 = a user was added to a security group / 4733 removed

4688 = log an event every time a process is launched

Sysmon IDs

1 = provides more detail than 4688

11 = file create / 13 registry value set

3 = network connection / 22 = DNS query

-----------

### Sysmon logs

Sysmon is a free tool for advanced monitoring

Important sysmon fields :

- Process info = context of the launched process

- Parent info = context of parent process

- Binary info = process hash, signature, metadata

- User content = a user running the process

--------------

### Powershell

Powershell is a powerful tool for the attackers because it's trusted and capable of installing malware, data exfil, discovery

it only creates one process, activity can be dificult to detect using only process creation

Powershell has a history file at C:\Users\<USER>\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadline\ConsoleHost_history.txt

with a history of all commands eecuted by powershell

---------

