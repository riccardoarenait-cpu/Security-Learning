# web stacks

MERN (MongoDB, Express.js, React, Node.js) = full common javascript stack, everywhere, saas produts, Node.js code often vulnerable

on ubuntu, express listening from port 5000, 3000, 27017 (X-Powered-By: Express), connect sid

prototype pollution 

Next.js = React framework for building full stack applications; X-Powered-By: Next.js port 3001

Middleware : function that runs before the request reaches the page, gatekeeper

vulnerability = the header x-middleware-subrequest prevents infinite loops so middleware will stop running, if you include it in your own request you can bypass it

 curl -H "x-middleware-subrequest: middleware:middleware:middleware:middleware:middleware" http://10.112.160.74:3001/dashboard

 Django = python native framework backend, port 8000 ubuntu, SQL injection vulnerability, order_by  

 LAMP (Linux, Apache, MySQL, and PHP) = popular open source stack used to host dynamic web application

 vulnerabilities = exposed PHP files, database errors, weak file permissions, and misconfigured Apache/PHP settings

 Nikito = automate 

 nikto -h http://10.112.134.89:3000 MERN

 nikto -h http://10.112.134.89:3001 Next.js

 nikto -h http://10.112.134.89:8000 Django

 nikto -h http://10.112.134.89:8080 Apache

 **SIMULATION**

 in this simulation I used the commands learned to exploit vulnerabilities across systemss

 <img width="1386" height="946" alt="image" src="https://github.com/user-attachments/assets/caa3b9a6-78e7-4f25-9485-1af65372f6a7" />
