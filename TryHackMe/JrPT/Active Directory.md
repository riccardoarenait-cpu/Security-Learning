# Active Directory

Microsoft's Active Directory  stores information about network objects, proides authentication and authorization services, and allows a centralized management of resources

Domain controller : server that runs AD services

Active Directory Domain Service :  stores information about all of the objects that exist on the network

Authentication :

- Kerberos = default windows protocol, Ticket based, the user authenticates with the domain controller and receives a ticket that can be presented to the services

- NetNTLM = Legacy authentication protocol, the client authenticates to the server they want to access, the service verifies the user's identity against the domain controller

-----------

### AD breaching

Gaining an initial set of credentials into AD

Attack surface : SMB, LDAP, HTTP, Kerberos, DNS

Username enumeration using OSINT, Kerbrute

Credential discovery : it's useful to look in places where developers could have left them, Git repositories, CI/CD platforms, file shares













