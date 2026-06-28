# Insecure Direct Object Reference

When the application provides an object to a user that isn't allowed to access it, it doesn't verify the user

access control vulnerability

example : https://onlinestore.thm/order/1000/invoice  -->  https://onlinestore.thm/order/1324/invoice

if encoded, decode, change parameters, encode again with same mechanism

if hashed, use reverse lookup tables

if it's a randomly generated string, create account A and account B, and see if you can switch up the accounts without authentication

Vulnerability is found in : background requests, javascript files, parameter mining, common locations
