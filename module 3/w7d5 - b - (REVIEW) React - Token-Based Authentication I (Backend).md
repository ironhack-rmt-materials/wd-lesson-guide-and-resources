

# React - Token-Based Authentication I (Backend)


<!-- 

status: draft

-->


<!--

Jan 2024: see PR JWT middleware simplified

- https://github.com/ironhack-labs/lesson-code-h-react-authentication-backend/pull/14

- https://github.com/jorgeberrizbeitia/lesson-code-h-react-authentication-backend/blob/938643359c4a7edf6b28f7169a93d3b7a216df37/middleware/jwt.middleware.js


Update (March 2024):
- PR applies to repo with the final code
- Will also be fixed in the students portal in the next re-run.
- Ironlauncher ?


-->





## Intro


- Quick refresh "the concern on users' security"
  - We will not store passwords
  - We store a representation: `HASH`




## Read & understand code generated by Ironlauncher --auth --json

<!-- 
@Luis: use code as it is  (do not change anything)
-->



POST /auth/signup
- ask students to read the code [3-4min]
- explain
- test with Postman

POST /auth/login
<!-- @LT: explain JWT once we reach that code in /login (not before)  -->
- ask students to read the code [5min]
- explain route + `explain JWT` (details below)
- test with Postman
  
POST /auth/verify:
- explain
- test with Postman



Summary:

  ```js
    // POST	/auth/signup
    router.post("/auth/signup", (req, res, next) => {
        /*
        - get info from req.body
        - validation
        - check if user already exists
          - if user exists: send error message   
          - if user doesnt exist....
            - generate salt + generate hash
            - User.create()
            - send response
        */
    })


    // POST  /auth/login 
    router.post("/auth/login ", (req, res, next) => {
        /*
        - get info from req.body
        - validation
        - User.findOne({email: req.body.email})
        - if user doesnt exist: send error
        - if user exists...
            - bcrypt.compareSync(req.body.password, hash);
                - if credentials are correct: sign jwt + send it in the response
        */
    })

  ```



## JSON Web Tokens (JWT)


- JWT Diagram: https://education-team-2020.s3.eu-west-1.amazonaws.com/web-dev/m3/token-auth/jwt-authentication-flow-1.png

- Token-based authentication is stateless, which means no information is stored on the server.

<!-- @todo: create diagrams -->

Token == "a document that is signed" (anyone in possession )


`jwt.sign` (payload + secret + header):
- https://education-team-2020.s3.eu-west-1.amazonaws.com/web-dev/m3/token-auth/jwt-signature.png


- (brief) Session auth vs Token auth
  - Each have advantages and disadvantages
  - Advantages & Disadvantages: https://stackoverflow.com/a/71552858/11298742
  - In depth comparison: https://stackoverflow.com/a/35059874/11298742




## Implement protected routes

- Protect some routes using middleware





## Improve error handling

Protected routes: if we use ironlauncher, in `error-handling\index.js`, we can add the following:

  ```js
      if (err.name === "UnauthorizedError") {
        res.status(401).json({message: "invalid token..."});
      }
  ```

  Example: https://github.com/Ironborn-Ironhack-March-2022/ironborn-project-management-server/commit/d6bea33a492aeffa16408575d136324ed72abc21



## Extra resources

Video - Session vs Token Authentication in 100 Seconds (Fireship, 2min)
https://www.youtube.com/watch?v=UBUNrFtufWo



## (OLD) Steps to change from session to token-based authentication

- In the old versions of ironlauncher, --auth provides session-based authentication.

- Steps to follow to move from session to token-based auth:
  https://github.com/ironhack-rmt-resources/ironlauncher-jwt-auth

