

# React - Token-Based Authentication I (Backend)


<!-- 

status: draft

-->





## Intro



<!--

@Luis: have prepared (open) project from module 2 (library project)

-->


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


UPDATE OCT. 2022:
- ironlauncher --auth --json now does token based auth
- code in the students portal is almost the same as ironlauncher
- differences:
  - students portal uses `bcryptjs`, ironlauncher uses `bcrypt`
    - should be fine, I think both provide the same methods.
  - implement `protected routes` ("Establish Protected Routes")




- follow students portal 
  - test routes with Postman



<!-- 
@Luis: 
- use code as it is  (ex. for User model: name + email + password)
- do not change anything, otherwise we need even more time.
-->





Improvements:
- Protected routes: if we use ironlauncher, in `error-handling\index.js`, we can add the following:

  ```javascript
      if (err.name === "UnauthorizedError") {
        res.status(401).json({message: "invalid token..."});
      }
  ```

  Example: https://github.com/Ironborn-Ironhack-March-2022/ironborn-project-management-server/commit/d6bea33a492aeffa16408575d136324ed72abc21






## (OLD) Steps to change from session to token-based authentication

- In the old versions of ironlauncher, --auth provides session-based authentication.

- Steps to follow to move from session to token-based auth:
  https://github.com/ironhack-rmt-resources/ironlauncher-jwt-auth


