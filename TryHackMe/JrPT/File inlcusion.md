# File inclusion

Vulnerabilities that trick a web application into exposing or executing files meant to be unaccessible

Applications usually accept parameters in the URL telling what files to return

file inclusion vulnerabilities happen when there's not enough input validation for the requests

--------

## Directory traversal

Allows the attacker to read files outside the application's root directory

uses the function file_get_contents

Example : http://webapp.thm/get.php?file=../../../../etc/passwd

the dots are used to travel back the directories

on windows servers, target files are initialization files : boot.ini, win.ini

----------

## Local file inclusion

The difference is LFI uses the function include(), the server executes the code before returning its output

it can lead to remote file execution

Identifying LFI : 

Insert a random string to view the error message

for example  http://webapp.thm/index.php?lang=THM

Warning: include(languages/THM.php): failed to open stream: No such file or directory in /var/www/html/THM-4/index.php on line 12

This error message shows the include function being used and how many directory levels there are

http://webapp.thm/index.php?lang=../../../../etc/passwd%00

these parameters will travel back the directories and add a null byte at the end to remove the .php

------------

## Remote file inclusion

The difference with LFI is, the attacker will point to a file from a server they control, not limited to the existing files in the target

it relies on the function allow_url_fopen, which accept URLs as input

successful attacks include XSS, DoS, information disclosure
