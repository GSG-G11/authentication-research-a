# Session-management in Express

![](https://i.imgur.com/TRQp8Hs.png)

## What are sessions?

**A website is based on the HTTP protocol. HTTP is a stateless protocol which means at the end of every request and response cycle, the client and the server forget about each other.**

This is where the session comes in. A session will contain some unique data about that client to allow the server to keep track of the user’s state. In session-based authentication, the user’s state is stored in the server’s memory or a database.

![](https://i.imgur.com/Jvt7Mlo.png)

## What are the different ways of managing sessions in express?


A cookie is a key-value pair that the browser stores. Every HTTP request delivered to the server is accompanied by cookies from the browser.

You can't save a lot of information in a cookie. Any kind of user credentials or secret information cannot be stored in a cookie. If we did so, a hacker might simply gain access to that information and use it for bad purposes.

The session data, on the other hand, is saved on the server side, in a database or a session store. As a result, it can handle higher volumes of data. A session is authenticated with a secret key or a session id that we acquire from the cookie on every request to access data from the server-side.

```js
app.use(session({
  'secret': '12345'
})
```

![](https://i.imgur.com/2SLsQ7M.png)

## Create a minimal example of how to set up a session (FYI: pseudo code is fine)

1. first you need to install package **express-session**.
 **`npm install express-session`**
2. you can instantiate it in your application with.
 **`const session = require('express-session')`**
3. you can use express.js because the session is middleware.
 ```js
 const app = express()
app.use(session({
  'secret': '343ji43j4n3jn4jk3n'
}))
```

**After this is done, all the requests to the app routes are now using sessions.**

4. you can access it using **req.session** to get data out of the session, and also to set data:
```js
req.session.name = 'Flavio'
console.log(req.session.name) // 'Flavio'
```

### Resourses:

* [Express Sessions](https://flaviocopes.com/express-sessions/#:~:text=When%20implemented%2C%20every%20user%20of,maintained%20by%20the%20Express%20team.&text=After%20this%20is%20done%2C%20all,routes%20are%20now%20using%20sessions)
* [Session Management in Node.js](https://www.section.io/engineering-education/session-management-in-nodejs-using-expressjs-and-express-session/)

* https://www.youtube.com/watch?v=hKYjSgyCd60
* https://youtu.be/oYGhoHW7zqI 