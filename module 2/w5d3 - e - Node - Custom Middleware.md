

# Node - Custom Middleware


## Custom middleware for user authorization

@students: 
- students portal includes a very detailed explanation, they may find it useful (login process, sessions, etc  )


Explain:
- middleware
  - ![diagram](./images/express-middleware.png)
- custom middleware
- middleware as an intermediate argument in our routes. eg:
  
  ```javascript
  router.get('/admin', isUserLoggedIn, () => {
    ...
  })
  ```


Make an example with different roles (eg. req.user.admin, req.user.collaborator):
- create middleware functions in the directory `/middleware` (note: in assessment they are in `/utils/middleware`).
- protect our routes. eg: GET `/create-thing`, GET `/delete-thing`
- if not allowed, redirect to login




## Ironlauncher with Auth boilerplate

- Command: `npx ironlauncher just-a-demo --auth`
  - IMPORTANT: remind students to select the option "views"

<!--

  In case Ironlauncher didn't install dependencies correctly:

  - npm i bcrypt@5.0.1 connect-mongo@4.6.0 cookie-parser@1.4.6 dotenv@16.0.3 express@4.18.1 express-session@1.17.3 hbs@4.2.0 mongoose@6.6.4 morgan@1.10.0 serve-favicon@2.5.0

  - npm i nodemon@2.0.20 --save-dev

-->


- Demo: run & explain what it has created
  - package.json
    - scripts 
    - installed bcryptjs, connect-mongo and express-session
  - /config/index.js added configuration for sessions
  - /routes/auth.js
    - signup
      - note: we have automatic login
    - login
    - logout
      - note: it's a GET request
  - /middlewares



- Students can use that to generate project-2

