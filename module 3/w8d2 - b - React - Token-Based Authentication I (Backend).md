

# React - Token-Based Authentication I (Backend)


<!-- 

status: just some notes

follow students portal (highlighted)


@Luis: have prepared (open) project from module 2 (library project)

-->



Notes:
- Code in the students portal is a bit different than the one created with `ironlauncher --auth --json` (tell students in case the compare or copy code from the students portal)



<!-- IMPORTANT  -->
<!-- IMPORTANT  -->
<!-- IMPORTANT  -->

- If we created app with `ironlauncher --auth --json`, just move from sessions to jwt.

- Here's a readme with the steps to follow:
  https://github.com/ironhack-rmt-resources/ironlauncher-jwt-auth

<!-- // IMPORTANT  -->
<!-- // IMPORTANT  -->
<!-- // IMPORTANT  -->






Bearer:
- The name "Bearer authentication" can be understood as "give access to the bearer of this token".




## Intro



- Session-based auth (module2) vs. tokens (module3)
  - Module 2 diagram: 
    - session (server keeps information about the state of the user)
    - sessionId (sent on each request)
  - JWT Diagram: https://education-team-2020.s3.eu-west-1.amazonaws.com/web-dev/m3/token-auth/jwt-authentication-flow-1.png
  - Token-based authentication is stateless which means that no information is stored on the server.

  - Session vs. token auth (diagram):
    - https://camo.githubusercontent.com/10cd8f8251ec9d1acf0d6c7e26d69415575c0f94b27c26c99c893e1743d6f4a2/68747470733a2f2f63646e2e61757468302e636f6d2f626c6f672f636f6f6b6965732d76732d746f6b656e732f636f6f6b69652d746f6b656e2d617574682e706e67

<!-- @todo: create diagrams -->



## Codealong
- follow students portal 
  - test routes with Postman
  - code for sessions: make cleanup as we go + at the end

Note:
- students portal uses `bcryptjs`, ironlauncher uses `bcrypt`
  - should be fine, I think both provide the same methods.


- JWT Validation Middleware:
  - import changes a bit with a recent version of the package (students portal is updated)
  - import with `const{expressjwt: jwt} = require("express-jwt");`


- Routes not needed
  - if we created with ironlauncher, we can remove these 2 routes:
    - GET loggedin
    - GET logout

<!-- 
@Luis: 
- use code as it is  (ex. for User model: name + email + password)
- do not change anything, otherwise we need even more time.
-->


Fix (if we follow students portal):
<!-- note: does not affect if we created with "ironlauncher auth" -->
- current version in the students portal has a bug when we try to create an account with the same email address
  - affects: current/old versions of the materials (does not affect ironlauncher)
  - endpoint `POST /signup`
  - details: https://github.com/ironhack-edu/web-bootcamp/issues/122
- solution: 
  - throw an error to break the promise chain
  - example: https://github.com/Ironborn-Ironhack-March-2022/ironborn-project-management-server/commit/c6b7b70d5e2a7131c5b019aad38cc804d455234e



Improvements:
- Protected routes: if we use ironlauncher, in `error-handling\index.js`, we can add the following:

  ```javascript
      if (err.name === "UnauthorizedError") {
        res.status(401).json({errorMessage: "invalid token..."});
      }
  ```

  Example: https://github.com/Ironborn-Ironhack-March-2022/ironborn-project-management-server/commit/d6bea33a492aeffa16408575d136324ed72abc21


## Cleanup

If we created with `ironLauncher --auth`
- remove all middleware that checks sesssion
- remove: `req.session`
- npm uninstall express-session connect-mongo
- middleware `isLoggedOut`, `isLoggedIn`