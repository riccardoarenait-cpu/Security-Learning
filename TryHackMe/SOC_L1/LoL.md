# Living off the land attacks

LoL attacks happen when the attacker uses trusted built in tools, widely available and allowed by default controls

Examples :

- Powershell

- WMIC = to run commands on hosts

- Certuil = fetch files, decode and encode payloads

- Rundll32 = DLL exports or URL handlers

  ------------

###  Detecting LoL

Powershell : usage of commands like IEX and -EncodedCommand to hide the payload and artifacts

WMIC : usage of commands like process call create, to download and execute a script, it often blends in with admin traffic

Certuil : usage of commands like -urlcache -split -f, it fetches a URL and writes it in a specified path

-------------
