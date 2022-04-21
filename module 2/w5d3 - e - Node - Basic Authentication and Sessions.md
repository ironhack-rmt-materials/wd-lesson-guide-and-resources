



# Node - Basic Authentication and Sessions

<!--

@todo: 
- provide boilerplate code with steps 1-4 (or at least 1-2) already done (students would clone, avoiding all those steps that by now they should know)


@Luis: follow students portal (~~highlighted, july21~~)

-->

- 2 parts:
  - Part 1: login process
  - Part 2: persistance (session & cookies)


## Login

- See "Step 4: functionality to login":
  https://github.com/Coding-Ninjas-Ironhack-Sept-2021/basic-auth-express-mongoose


## Data persistence using session and cookies

- See how, when we refresh the page, we loose the user details

- Explanation: HTTP is a stateless protocol
  - "every time a new request is sent from the client to the server, the information about the previous request is lost"


- Sessions

- Cookies

- Demo

- IMPORTANT: keep user logged in
  - to keep login in development (ie. when we change code and nodemon restarts the server), make sure the property "ttl" is not commented:

  ```
  store: MongoStore.create({
    mongoUrl: MONGO_URI,
    ttl: 60 * 60
  }),
  ```

## Bonus & Extra challenges:

- Display "Logout" button only if user is logged-in.

- Implement header with:
  - If user is logged-in: display the message "Welcome ${username}" + Logut button
  - If user is logged-out: display "Register" + "Login" buttons


