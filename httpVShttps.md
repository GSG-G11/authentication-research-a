
HTTP is a protocol for fetching resources such as HTML documents. It is the foundation of any data exchange on the Web 

# HTTPS 
Hypertext transfer protocol secure (HTTPS) is the secure version of HTTP, which is the primary protocol used to send data between a web browser and a website. HTTPS is encrypted in order to increase security of data transfer. This is particularly important when users transmit sensitive data, such as by logging into a bank account.

### How does HTTPS work?

HTTPS uses an encryption protocol to encrypt communications. The protocol is called Transport Layer Security (TLS), although formerly it was known as Secure Sockets Layer (SSL). This protocol secures communications by using what’s known as an asymmetric public key infrastructure. This type of security system uses two different keys to encrypt communications between two parties:

The private key - this key is controlled by the owner of a website and it’s kept. This key lives on a web server and is used to decrypt information encrypted by the public key.

The public key - this key is available to everyone who wants to interact with the server in a way that’s secure. Information that’s encrypted by the public key can only be decrypted by the private key.


# What are TLS/SSL certificates?

-- Transport Layer Security is a protocol that establishes an encrypted session between two computers on the Internet. It verifies the identity of the server and prevents hackers from intercepting any data.
### TLS certificates:
- are a type of digital certificate, issued by a Certificate Authority (CA). The CA signs the certificate, certifying that they have verified that it belongs to the owners of the domain name which is the subject of the certificate.
- TLS certificates usually contain the following information:

  -The subject domain name
  -The subject organization
  -The name of the issuing CA
  -Additional or alternative subject domain names,      including subdomains, if any
  -Issue date
  -Expiry date
  -The public key (The private key, however, is a    secret.)
  -The digital signature by the CA
  
### How does a TLS certificate work?
When a user tries to connect to a server, the server sends them its TLS certificate.

The user then verifies the server’s certificate using CA certificates that are present on the user’s device to establish a secure connection. This verification process uses public key cryptography, such as RSA or ECC, to prove the CA signed the certificate

 ![](https://i.imgur.com/KVAHXry.png)


# Why is https important to implement in your projects?

### Website integrity
HTTPS prevents any third-party interference with how your website communicates with its users. These interferences can originate from hackers wishing to exploit your website’s vulnerabilities, as well as intrusive companies that wish to “inject” their own advertisements on your website. As an example, an intrusive company may easily fill your website with their own ads, thus ruin the entire website browsing experience for your users.

### Protects user sensitive data
One of the main benefits of HTTPS is that it adds security and trust. It protects users against man-in-the-middle (MitM) attacks that can be launched from compromised or insecure networks. Hackers can use such techniques to steal your customer’s sensitive information.

### Confidence
The green padlock which appears on a secured site can give customers peace of mind that your website can be trusted and their information is safe, this can lead to increased conversion and loyalty.

### Mobile technology
There is another important advantage in switching to HTTPS. No serious modern business can afford to overlook mobile technology. Making sure that your site is mobile-friendly by considering such factors as page loading speed, is as crucial to success in the modern marketplace as employing the latest in SEO strategy.
 
![](https://i.imgur.com/4TwsLq1.png)

![](https://i.imgur.com/OZQ8vd9.png)






