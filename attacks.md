# Authentication attacks

## Man In The Middle (MITM)

### What is MITM Attack

A man in the middle (MITM) attack is a general term for when a perpetrator positions himself in a conversation between a user and an application—either to eavesdrop or to impersonate one of the parties, making it appear as if a normal exchange of information is underway.

### MITM Attack Process

<img src="https://info.varonis.com/hs-fs/hubfs/Imported_Blog_Media/how-does-mitm-attack-work.png?width=1240&height=1129&name=how-does-mitm-attack-work.png">

#### In this example, there are three entities, Ali, Basel, and Monther (the attacker).

- Monther covertly listens to a channel where Ali and Basel are communicating.
- Ali sends a message to Basel.
- Monther intercepts and reads Ali’s message without Ali or Basel knowing.
- Monther alters messages between Ali and Basel, causing unwanted/damaging responses.

### How to Detect a MITM Attack

<img src="https://info.varonis.com/hs-fs/hubfs/Imported_Blog_Media/how-to-detect-man-in-the-middle-attack.png?width=1240&height=1125&name=how-to-detect-man-in-the-middle-attack.png">

### Signs to Look For

- **Unexpected and/or repeated disconnections**
  - Attackers forcefully disconnect users so they can intercept the username and password when the user tries to reconnect.
- **Strange addresses in your browser address bar**
  - If anything in the address looks odd, even by a little, double-check it. It could be a DNS hijack. For example, you see https:\\\www.go0gle.com instead of https:\\\www.google.com
- **You log into a public and/or unsecured Wi-Fi**
  - Be very careful of what networks you connect to, and avoid public Wi-Fi if possible. Attackers create fake networks with known IDs like “local free wireless” or some other common name to trick people into connecting. If you connect to the attacker’s Wi-Fi, they can easily see everything you send on the network.

### How to Prevent a MITM Attack

<img src="https://info.varonis.com/hs-fs/hubfs/Imported_Blog_Media/mitm-prevention.png?width=1241&height=905&name=mitm-prevention.png">

### General Best Practices

#### For Normal Users

- Only connect to secured Wi-Fi routers.
- Add a VPN to encrypt traffic between end-points and the VPN server. If traffic is encrypted, it’s harder for a MiTM to steal or modify it.
- Use end-to-end encryption for your emails, chat, and video communication (Whatsapp, Zoom, MS Teams, etc.)
- Keep the system patched and malware updated.
- Use a password manager to protect your passwords and prevent reuse of passwords.
- Use multi-factor authentication wherever available.

#### For Developers

- Use `secure` flag when adding cookies to a browser.
- It is considered best practice for applications to use SSL/TLS to secure every page of their site and not just the pages that require users to log in.
- Doing so helps decreases the chance of an attacker stealing session cookies from a user browsing on an unsecured section of a website while logged in.

## Cross Site Scripting (XSS)

### What is XSS ?

Cross-Site Scripting (XSS) attacks are a type of injection, in which malicious scripts are injected into otherwise benign and trusted websites. XSS attacks occur when an attacker uses a web application to send malicious code, generally in the form of a browser side script, to a different end user. Flaws that allow these attacks to succeed are quite widespread and occur anywhere a web application uses input from a user within the output it generates without validating or encoding it.

An attacker can use XSS to send a malicious script to an unsuspecting user. The end user’s browser has no way to know that the script should not be trusted, and will execute the script. Because it thinks the script came from a trusted source, the malicious script can access any cookies, session tokens, or other sensitive information retained by the browser and used with that site. These scripts can even rewrite the content of the HTML page.

![](https://i.imgur.com/3nXmisr.png)
![](https://i.imgur.com/bG72VGx.png)

### Types of XSS

#### Reflected XSS

Reflected attacks are those where the injected script is reflected off the web server, such as in an error message, search result, or any other response that includes some or all of the input sent to the server as part of the request. Reflected attacks are delivered to victims via another route, such as in an e-mail message, or on some other website. When a user is tricked into clicking on a malicious link, submitting a specially crafted form, or even just browsing to a malicious site, the injected code travels to the vulnerable web site, which reflects the attack back to the user’s browser. The browser then executes the code because it came from a “trusted” server. Reflected XSS is also sometimes referred to as Non-Persistent or Type-II XSS.

#### Stored XSS

Stored attacks are those where the injected script is permanently stored on the target servers, such as in a database, in a message forum, visitor log, comment field, etc. The victim then retrieves the malicious script from the server when it requests the stored information. Stored XSS is also sometimes referred to as Persistent or Type-I XSS.

#### DOM XSS

It is an XSS attack wherein the attack payload is executed as a result of modifying the DOM “environment” in the victim’s browser used by the original client side script, so that the client side code runs in an “unexpected” manner. That is, the page itself (the HTTP response that is) does not change, but the client side code contained in the page executes differently due to the malicious modifications that have occurred in the DOM environment.

![](https://i.imgur.com/1romlh8.png)

### Solution

#### Keep Software Up-To-Date

Regularly updating software will greatly reduce the vulnerabilities that leave a site or application open to XSS vulnerabilities.

#### Content Security Policy

A content security policy (CSP) can define the functions a website is allowed to perform. They can be used to prevent a website from accepting any in-line scripts. This may be the strongest method at your disposal as it can completely block XSS attacks or at least greatly reduce the possibility of them.

#### DOMPurify

sanitizes HTML and prevents XSS attacks. You can feed DOMPurify with string full of dirty HTML and it will return a string (unless configured otherwise) with clean HTML. DOMPurify will strip out everything that contains dangerous HTML and thereby prevent XSS attacks and other nastiness. It's also damn bloody fast. We use the technologies the browser provides and turn them into an XSS filter. The faster your browser, the faster DOMPurify will be.

## Cross Site Request Forgery (CSRF):

Cross-site request forgery (also known as CSRF) is a web security vulnerability that allows an attacker to induce users to perform actions that they do not intend to perform. It allows an attacker to partly circumvent the same origin policy, which is designed to prevent different websites from interfering with each other.

![](https://i.imgur.com/g3xeUWq.png)

### Prevention of Cross Site Request Forgery (CSRF):

1. #### Synchronizer token pattern

   is a technique where a token, secret and unique value for each request, is embedded by the web application in all HTML forms and verified on the server side. The token may be generated by any method that ensures unpredictability and uniqueness (e.g. using a hash chain of random seed). The attacker is thus unable to place a correct token in their requests to authenticate them

2. #### Double Submit Cookie

   Similarly to the cookie-to-header approach, but without involving JavaScript, a site can set a CSRF token as a cookie, and also insert it as a hidden field in each HTML form. When the form is submitted, the site can check that the cookie token matches the form token. The same-origin policy prevents an attacker from reading or setting cookies on the target domain, so they cannot put a valid token in their crafted form.

   The advantage of this technique over the Synchronizer pattern is that the token does not need to be stored on the server.

3. #### SameSite cookie attribute
   An additional "SameSite" attribute can be included when the server sets a cookie, instructing the browser on whether to attach the cookie to cross-site requests. If this attribute is set to "strict", then the cookie will only be sent on same-site requests, making CSRF ineffective. However, this requires the browser to recognise and correctly implement the attribute, and also requires the cookie to have the "Secure" flag.
