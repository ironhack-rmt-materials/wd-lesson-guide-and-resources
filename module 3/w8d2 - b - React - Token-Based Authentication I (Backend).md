

# React - Token-Based Authentication I (Backend)


<!-- 

status: just some notes

follow students portal (highlighted)

-->




Notes:
- Code in the students portal is a bit different than the one created with `ironlauncher --auth --json` (tell students in case the compare or copy code from the students portal)


Bearer:
- The name "Bearer authentication" can be understood as "give access to the bearer of this token".



If we create app with `ironlauncher --auth`:
- cleanup req.session



## Intro



- Session-based auth (module2) vs. tokens (module3)
  - Module 2 diagram: 
    - session (server keeps information about the state of the user)
    - sessionId (sent on each request)
  - JWT Diagram: https://education-team-2020.s3.eu-west-1.amazonaws.com/web-dev/m3/token-auth/jwt-authentication-flow-1.png
  - Token-based authentication is stateless which means that no information is stored on the server.

<!-- @todo: create diagrams -->



## Codealong
follow students portal



Improvements:
- Protected routes: if we use ironlauncher, in `error-handling\index.js`, we can add the following:

  ```javascript
      if (err.name === "UnauthorizedError") {
        res.status(401).json({message: "invalid token..."});
      }
  ```


## Cleanup

If we created with `ironLauncher --auth`
- remove all middleware that checks sesssion
- remove: `req.session`
- npm uninstall express-session connect-mongo
- middleware `isLoggedOut`, `isLoggedIn`