# Server Side Request Forgery

Allows the attacker to cause a server side application to make http requests to a destination of choice, attacker manipulates a parameter, redirecting the request 

it exploits the trust between internal systems

Regular : the response is returned in the application's front end response

Blind : response isn't visible

Attack vectors = 

Full URL in a parameter = application accepts a full URL as input and uses it to make the request

Partial URL = some applications accept hostname and construct the URL 

Path trasversal = Redirecting trajectories 

Hidden form fields = HTML page source embedded

------------------

Confirming a blind SSRF 

1 External HTTP logger 

2 Burp collaborator 

3 Self hosted listener

4 Timing analysis

5 Error based
