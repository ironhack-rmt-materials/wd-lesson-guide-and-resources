

# React - Token-Based Authentication I (Backend)


<!-- 

status: just some notes

follow students portal (highlighted)

-->



Notes:
- Code in the students portal is a bit different than the one created with `ironlauncher --auth --json` (tell students in case the compare or copy code from the students portal)



<!-- IMPORTANT  -->
<!-- IMPORTANT  -->
<!-- IMPORTANT  -->

- If we created app with `ironlauncher --auth --json`, just move from sessions to jwt.

- Here's a readme with the steps to follow:
  https://github.com/Ironmaidens-Ironhack-Jan-2022/ironlauncher-jwt-auth

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

<!-- @todo: create diagrams -->



## Codealong
follow students portal

<!-- 
@Luis: 
- use code as it is  (ex. for User model: name + email + password)
- do not change anything, otherwise we need even more time.
-->


Fix (if we follow students portal):
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
        res.status(401).json({message: "invalid token..."});
      }
  ```

  Example: https://github.com/Ironborn-Ironhack-March-2022/ironborn-project-management-server/commit/d6bea33a492aeffa16408575d136324ed72abc21


## Cleanup

If we created with `ironLauncher --auth`
- remove all middleware that checks sesssion
- remove: `req.session`
- npm uninstall express-session connect-mongo
- middleware `isLoggedOut`, `isLoggedIn`