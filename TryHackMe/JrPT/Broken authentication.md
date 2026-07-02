# Broken authentication

Authentication is the process of verifying the user's identity, the application server compares the credentials submitted with records held in credential stores

Bypass attacks require stealing credentials, session tokens, or exploting assumptions of developers

Authentication bypass types :

- Username enumeration = submit usernames to a form that responds differently for registered and unregistered names

- Credential brute force = pair valid usernames with passwords and submit until a pair is working

- Logic flaws = Use valid input to redirect authentication flow

- Cookie manipulation = edit session state to change the authentication decision

  ------------

  ### ffuf as enumeration tool

  ffuf can be used as username enumeration tool, it sends POST requests to signup forms and lists the usernames that get the response "An account with this username already exists"

  Example of command : ffuf -w /usr/share/wordlists/SecLists/Usernames/Names/names.txt -X POST -d "username=FUZZ&email=x&password=x&cpassword=x" -H "Content-Type: application/x-www-form-urlencoded" -u http://10.114.177.174/customers/signup -mr "username already exists"

  -w selects the wordlist, -X POST sets the HTTP method, -d the request body, -H the content type, -u target URL, -mr resricts output to fixed responses

  <img width="1887" height="912" alt="image" src="https://github.com/user-attachments/assets/dce3d964-1d7e-49cd-b396-dd462dd704f6" />

  in this screenshot I tried the command I listed earlier against a target test machine

  ### fuff as Credential brute forcer

  fuff can be used as a brute forcer, it sends requests with credentials from a wordlist and registers valid logins when a website returns a 302 redirect

  Example of command : ffuf -w valid_usernames.txt:W1,/usr/share/wordlists/SecLists/Passwords/Common-Credentials/10-million-password-list-top-100.txt:W2 -X POST -d "username=W1&password=W2" -H "Content-Type: application/x-www-form-urlencoded" -u http://10.114.177.174/customers/login -fc 200

  this command binds two wordlists, the username one identified with W1, the password one identified with W2, -fc 200 discards responses that returned 200 leaving only logins visible

  <img width="1834" height="677" alt="image" src="https://github.com/user-attachments/assets/efeee10c-7f51-4797-b2d1-9673e4f2c072" />

  in this screenshot I used the command I listed earlier against a test macine and found a username and password working pair

  --------------

  ## Logic flaws

  an application's flow can be redirected by providing input the developer didn't anticipate

  not found by automated scanners

  ### Case sensitive path comparison

  When two components disagree o input interpretation it created a vulnerability

  if the Router is not case sensitive but the authntication algorithm is, the attacker could input /adMin and the router would skip the algorith because it only checks for /admin inputs

  ------------------

  

  
  

  









  







  
