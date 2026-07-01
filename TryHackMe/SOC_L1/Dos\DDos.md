# DoS/DDoS

Attacks designed to overwhelm an application to make it unavailable

it's considered successful if it prevents a service from functioning properly

DDoS uses many machines, usually through botnets

Attack types : 

- Slowloris = sending many partial HTTP requests

- HTTP flood = sending a lare number of HTTP requests

- Cache bypas = bypassing CDN servers and forcing the original server's response

- Oversized query = Forcing servers to process large requests

- Login form abuse = overloading authentication with attempts

Attack motives = Financial loss, extortion, hacktivism, distracton, competition, reputational damage

-----------

### Indicators of compromise

Here are common indicators found in log analysis

- High request rate : 1000 GET /login

- Odd user agent : curl, python-urllib

- Geographic anomalies

- Server error spike 503

- Logic abuse

  -----------

  ## Mitigation techniques

  **Application level**

  - a secure code must be deployed so that search fields and forms can't be abused
 
  - CAPTCHA against botnets
 
  **Network level**

  - applying CDN; reduces latency and provide load balancing
 
  - WAFs
 
    



