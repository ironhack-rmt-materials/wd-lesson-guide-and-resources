# Websockets


## Setup with Express (so that it can be deployed in heroku)

Configuration for Node.js and Express.js are a bit different.
Make sure to use configuration for Express.js (you will avoid problems deploying to heroku).


Configuration for Express:


```javascript
    const app = require('express')();
    const server = require('http').createServer(app);
    const io = require('socket.io')(server);
    io.on('connection', () => { /* … */ });
    server.listen(3000);
```

Source: https://www.npmjs.com/package/socket.io#user-content-in-conjunction-with-express



Also, need to add cors setting to web socket:

```javascript
    const io = require('socket.io')(server,{
        cors: {
            credentials: true,
            origin: process.env.ORIGIN || "http://localhost:3000",
        },
    });
```


## Example:

Backend: https://github.com/J-S-app/js-fullstack-webapp-server
Frontend: https://github.com/J-S-app/js-fullstack-webapp-client

