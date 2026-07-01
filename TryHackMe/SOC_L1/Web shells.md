# Web shells 

A web shell is a malicious programm installed on a target server, it allows initial access and persistence to an attacker

Once access is gained, a web shell is used to move through the kill chain

The vulnerability exists when the application fails to validate file type, shells can be in .php or .aspx

It usually abuses legitimate execution functions

------

### Indicators of compromise

Web logs = shells rely on web server abuse, web server logs can carry evience

Unusual HTTP methods :

- GET = repeated GET can be used for recon

- POST = upload or interact with the shell

- PUT = upload a shell

- DELETE = cleanup of evidence

- OPTIONS = recoinnassance

- HEAD = detect files

  Suspicious user agents, query strings with cmd or exec or encoded

-----------

An attacker's shell must be stored somewhere, analyzing web server files is crucial

in apache shells are usually placed at /var/www/html/

in Nginx, /usr/share/nginx/html/

**Helpful commands**

find = to search for recently modified scripts

-newerct = to set two date ranges

grep = to track functions like eval()

Examples : find /var/www -type f -name "*.php" -newerct "2025-07-01" ! -newerct "2025-08-01"

grep -r "eval(" wp-content

-----------


  
