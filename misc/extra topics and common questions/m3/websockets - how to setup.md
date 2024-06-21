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






## Websockets connection

Note: 

Many hosting services set a timout limit for WS connections.
Example, Adaptable: https://drive.google.com/file/d/1Li-siYc6EGM-kC0l0NyZgm16Ee3KtKMt/view

To fix that, client needs to reconnect everytime the connection is lost.




## Project 3 examples

Moonlight events:
- Demo: https://moonlight-events.netlify.app/
- Backend: https://github.com/JoTa-Events/moonlight-server
- Frontend: https://github.com/JoTa-Events/moonlight-client
- Handle disconnection: https://github.com/JoTa-Events/moonlight-client/blob/main/src/components/ChatBox.js


PetHub (Cristian + Ismael):
- https://github.com/PetHub-MERN/pethub-client
- https://github.com/PetHub-MERN/pethub-server


Artist Connection (Greg + Jesus)
- Demo: https://artist-connection.netlify.app/
- Backend: https://github.com/mitte-script-society/artist-network-server
- Frontend: https://github.com/mitte-script-society/artist-network-client
- includes feedback when user's typing.

