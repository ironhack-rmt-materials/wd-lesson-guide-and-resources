

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

  Bug with dependencies: 
  - students with the dependencies bug will need to install manually "express-session" and "connect-mongo"

-->


- Demo: run & explain what it has created
  - installed bcryptjs, connect-mongo and express-session
  - /routes/auth.js
    - signup
      - note: we have automatic login
    - login
    - logout
      - note: it's a GET request
  - /middlewares
  - /config/index.js added configuration for sessions



- Students can use that to generate project-2

