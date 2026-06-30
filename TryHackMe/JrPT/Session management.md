# Session management

Lifecycle : 

- Session creation = when you visit a website a session is created, when you authenticate the session value gets received

- Session tracking = the value is submitted with every request, the web application tracks your actions

- Session expiry = when the session expires you're sent again to the login page

- Session termination = when a user performs logout action

IAAA model :

- Identification = verifying who the user is

- Authentication = ensuring the user is who they say they are

- Authorization = ensuring thr user has the rights to perform the action requested

- Accountability = creating a record of the actions performed by the user

-----------

Cookie based session management :

a session cookie will be assigned; Set-Cookie: session=12345;

Token Based Session Management :

uses client side javascript code, stored in the browser's local storage

-----------------

### Securing lifecycle

Session creation :

weak or controllable session values, can be guessed or reverse engineered

session fixation, if the application doesn't change the token after you authenticate

Session tracking :

Authorization bypass when there aren't sufficient checks on the user, vertical bypass and horizontal bypass;

Insufficient logging, only logging rejected actions is not enough

Session expiry : 

only vulnerability is too long expiry time

Session termination :

when sessions aren't properly terminated once the user logs out



  
