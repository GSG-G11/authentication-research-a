

# OAUTH 


## What Is OAuth?:

OAuth is an open-standard authorization protocol or framework that provides applications the ability for “secure designated access”.

More specifically, OAuth is a standard that apps can use to provide client applications with “secure delegated access”. OAuth works over HTTPS and authorizes devices, APIs, servers, and applications with access tokens rather than credentials.

 ---
## Why OAuth?

![](https://i.imgur.com/kZC6y1q.png)
OAuth was created as a response to the direct authentication pattern. This pattern was made famous by HTTP Basic Authentication, where the user is prompted for a username and password. Basic Authentication is still used as a primitive form of API authentication for server-side applications: 

- Instead of sending a username and password to the server with each request.
- The user sends an API key ID and secret.

**Before OAuth**, sites would prompt you to enter your username and password directly into a form and they would login to your data (e.g. your Gmail account) as you. This is often called the password anti-pattern.


---
## OAuth and APIs, How OAuth Is Used to Access APIs?

Companies need to **protect** their REST APIs in a way that **allows many devices to access them**. 

- In the old days, you’d enter your username/password directory.
- The app would login directly as you. => This gave rise to the delegated authorization problem.

![](https://i.imgur.com/BNZNbQ6.png)

1. App requests authorization from User.
2. User authorizes App and delivers proof.
3. App presents proof of authorization to server to get a Token.
4. Token is restricted to only access what the User authorized for the specific App (It enables apps to obtain limited access (scopes) ).

## OAuth 1.0 vs. OAuth 2.0 !! 

## OAuth 1.0
- Transport-independent. Security is not delegated to HTTPS/TLS.
- Founded in cryptography, especially digital signatures. 
- Messages are each individually cryptographically signed. If a single message within the communication is constructed or signed improperly, the entire transaction will be invalidated

## OAuth 2.0
- Transport-dependent. Most security defenses are delegated to HTTPS/TLS
- Centered around bearer tokens
- Much easier to work with. OAuth 2.0 is much more usable, but much more difficult to build securely.
- Much more flexible. OAuth 1.0 only handled web workflows, but OAuth 2.0 considers non-web clients as well.
- Better separation of duties. Handling resource requests and handling user authorization can be decoupled in OAuth 2.0.
