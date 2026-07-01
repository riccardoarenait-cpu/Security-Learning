# Web security

Web applications are one of the most common entry points for attackers, always available and exposed, they connect to databases and infrastructure

Cycle : When you visit a website, the browser sends requests to a web server, the server verifies access and returns a response to the user

Components of web service : 

- Application = the code, styles, looks and functions

- Web server : hosts the application, sits in front of it, publically exposed, examples are apache, nginx, iis

- Host machine : operating system

---------

### Protecting the application 

- Secure code : handling of errors, remove sensitive information

- Input validation : validate user input to prevent injection

- Access control : reduce access based on rules

------------

### Protecting the web server

- Logging : keep a detailed record of all requests

- Firewall : block harmful traffic

- CDN : reduce exposure to your servers

---------------

### Protecting the host machine 

- Least priviledge

- System hardening

- Antivirus

------------

### Content delivery networks

Store and serve cache content from servers closer to the user to reduce latency

Security advantages : IP masking, DDoS protection, Enforced HTTPS, integrated WAFs

------------------

### WAFs

Layer of protection for applications

- Cloud based : sits in front of web server and gret scalability

- Host based : deployed on the web server

- Network based : sits on network perimeter

















