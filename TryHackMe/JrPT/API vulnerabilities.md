# API Pentesting

API is an interface that enables software to communicate with each other

One API can serve multiple servers at one time, becoming a great attack surface

APIs can be exploited by checking endpoints that interact with them for vulnerabilities

### REST APIs

A common API style is REST, an architectual style developers follow to build web applications

Resource : any object or data exposed by the API, for example /v1/users, /v1/products

API request : HTTP method, endpoint URL, headers, body; 

Example : GET http://api.shop.local:8000/v1/products


----------


### Broken Object Level Authorization

The number 1 API risk

When the API returns  requested object without verifying if the user is permitted to access it

How it works : the user authenticated as user 4 is able to change the request to view user 1's data

------------

### Mass assignment

When API takes data from a client's request and applies it without checking which fields he's permitted to set

Useful for priviledge escalation
