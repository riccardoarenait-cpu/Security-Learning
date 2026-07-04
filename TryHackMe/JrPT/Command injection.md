# Command injection

When the application doesn't properly check user input, command injection are possible

the vulnerability exists because programming languages allow code execution through functions

Example :  $command = "grep $title /var/www/html/songtitle.txt"; 

grep ; cat /etc/passwd /var/www/html/songtitle.txt

### Blind injection

If the application doesn't respond verbally to the commands, there are ways to detect and exploit injection

Detection : using ping or sleep to see if the application takes time to respond ; ping -c 10 127.0.0.1

Exploitation : forcing output into a file ; whoami > /var/www/html/output.txt

### Remediation

- Careful handling of functions that interact with the servers : exec(), passthru(), system()

- Input validation, filtering for only the intended use, for example FILTER_VALIDATE_NUMBER

