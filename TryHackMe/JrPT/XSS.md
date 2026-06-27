# XSS

DOM = Document object model, the browser's live visible page, structured representation

URL parameters = bits after ? in an URL

Escaping = transforming data so that the browser reads it as plain text not as code

<script>alert('XSS')</script>  testing payload, injected into search fields, comments, profile names, feedback, URL parameters

Common intentions : session stealing, key logger, business logic attacks

Reflected XSS = the user input is immediately displayed on the page, it can read or modify the page, steal cookies 

Stored XSS = application saves input from the server and serves it to any visitor's browser

DOM based XSS = occours when javascript reads attacker's data from the DOM, and writes it back into the page unsafely

Blind XSS = the payload gets stored for another user to view but you can't use it yourself

to test for it, have a callback like http request

--------

If the word "script" is filtered out, <sscriptcript>alert('THM');</sscriptcript> 

onload="alert('THM'); lets you execute your own code after the image IMG has loaded
