#CSRF

an attacker tricks a browser into sending a request to a website where the user is already authenticated, abuses of trust relationship

Conditions : 

1 the victim must be authenticated to the application

2 the application must perform a state changing action

3 the application doesn't verify if the request came from a trusted source

Example of CSRF :

the goal is to change the email of an authenticated user on the test website staffhub.thm

1 create a web page that sends requests to the application's server

cd /var/www/html , nano settings.html , code

2 if a victim who is still authenticated in the website clicks on the page created, the request will be sent with the cookie

----------------------

How to spot :

1 Focus on state changing requests

2 inspect requests for CSRF tokens

3 analyse http methods, POST requests for sensitive actions 

4  test requests outside the application

5 observe cookie behaviour

