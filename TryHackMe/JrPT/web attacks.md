curl -sI http://10.112.182.15:PORT/    header request

curl -s http://10.112.182.15:PORT/nonexistent-page-xyz     get a different error code based on the server

Python's default HTTP server port 8000, quickly share files for developers, exposed public facing server

curl -s http://10.112.182.15:8000/    HTML page listing files it can see

.env file environment specific configuration

Apache has bult in status page, when misconfigured it is accessible at http://10.112.182.15:80/server-status, information on what users are doing and internal paths

.bak extensions worth checking

curl -s http://10.112.182.15:3000/api/routes     find routes to possible sensitie information

 curl -s http://10.112.182.15:3000/static/config.js    static files by Node.js

 curl -sI http://10.112.182.15:PORT | grep -i server      server header

 curl -s http://10.112.182.15:8080/nginx_status 


**SIMULATION** 

in this simulation I used the commands learned to map out servers and directories on the target machine

<img width="1383" height="953" alt="image" src="https://github.com/user-attachments/assets/fa9b5cf6-198b-4e8a-956b-0af3f4f44b78" />

