# Websockets


## Setup with Express (so that it can be deployed in heroku)

Configuration for Node.js and Express.js are a bit different.
Make sure to use configuration for Express.js (you will avoid problems deploying to heroku).


Configuration for Express:


```js
    const app = require('express')();
    const server = require('http').createServer(app);
    const io = require('socket.io')(server);
    io.on('connection', () => { /* … */ });
    server.listen(3000);
```

Source: https://www.npmjs.com/package/socket.io#user-content-in-conjunction-with-express



Also, need to add cors setting to web socket:

```js
    const io = require('socket.io')(server,{
        cors: {
            credentials: true,
            origin: process.env.ORIGIN || "http://localhost:3000",
        },
    });
```




## Guided Steps:

https://github.com/ManishPoduval/simple-chat-socketio



## Example of p3 project with websockets:

Note: had issue with socket.io disconnecting

Backend: 
- Repo: https://github.com/J-S-app/MeMedia-fullstack-webapp-server
- Server config: https://github.com/J-S-app/MeMedia-fullstack-webapp-server/blob/main/server.js


Frontend: 
- Repo: https://github.com/J-S-app/MeMedia-fullstack-webapp-client
- Component with WS: https://github.com/J-S-app/MeMedia-fullstack-webapp-client/blob/main/src/pages/Messages.jsx



## Another example of p3 project with websockets:

Notes:
- solved issue with socket.io disconnected
- deployed on adaptable


Demo: https://moonlight-events.netlify.app/
Backend: https://github.com/JoTa-Events/moonlight-server
Frontend: https://github.com/JoTa-Events/moonlight-client

Handle disconnection: https://github.com/JoTa-Events/moonlight-client/blob/main/src/components/ChatBox.js

