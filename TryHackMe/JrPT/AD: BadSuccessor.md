# AD: BadSuccessor

Active directory is a directory service for windows that stores information about network objects and provides authentication and authrization services

AD has different account types : 

- Standalone managed service account = designed for a signle computer

- Group Managed Service Account = designed for multiple computers or servers

- Delegated Managed Service Account = most recent addition

##  BadSuccessor

 BadSuccessor is a priviledge escalation vulnerability that abuses dMSA

 As a recoinnassance step in exploiting the vulnerability, I executed a script on the virtual machine that identified the accounts that can create dMSA

 <img width="513" height="159" alt="image" src="https://github.com/user-attachments/assets/742d9163-6fed-48d7-802a-5dc0c0261d5a" />

 Next I used SharpSuccessor, a proof of concept that weaponizes BadSuccessor, to create a dMSA impersonating an administrator

 <img width="610" height="375" alt="image" src="https://github.com/user-attachments/assets/3ae9294e-3f4d-4d0c-8a24-d311e20f56fd" />

 I then generated a ticket with Rubeus
 
<img width="610" height="403" alt="image" src="https://github.com/user-attachments/assets/095b8214-1099-43e7-b23b-8264d032882b" />

Using the ticket we can get the keys to request any service

<img width="611" height="394" alt="image" src="https://github.com/user-attachments/assets/fbda7b68-968a-4ddd-a13e-7d655bbd33b1" />

---------

### Mitigations

At the moment there is no patch from Microsoft, the way to mitigate it is to restrict the ability to create dMSA objects to administrators 














