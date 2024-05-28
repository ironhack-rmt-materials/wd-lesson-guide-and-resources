

# Node - Custom Middleware


## Custom middleware for user authorization

<!--
@students: 
- students portal includes a very detailed explanation, they may find it useful (login process, sessions, etc)
-->


Explain:
- middleware
  - ![diagram](../media/images/express-middleware.png)

  - diagram 2: https://education-team-2020.s3.eu-west-1.amazonaws.com/web-dev/m2/expressjs/express-middleware-1.png

  - (skip) diagram 3: https://res.cloudinary.com/practicaldev/image/fetch/s--PHYkGiKU--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/73eusy0bc095c9w8tstw.png



- Custom middleware

  <!-- @LT: search documentation for app.use() -->

  ```js
  app.use( (req, res, next) => {
    console.log("hello world")
    //next();
  });
  ```


- Middleware as an intermediate argument in our routes. eg:
  
  ```js
  router.get('/admin', isUserLoggedIn, () => {
    ...
  })
  ```


- Implement protected routes
  
  ```js
  const isLoggedIn = (req, res, next) => {
    if(req.session.currentUser){
        next();
    } else {
        res.redirect("/login")
    }
  }
  ```


- Protect C+U+D books


- Extract the middleware function to a separate file
  - Example: https://github.com/ironicHackers-Ironhack-Sept-22/ironic-library-project/commit/bb74239f42168550651a132c089f77cd165bbff4


- Explain: exporting multiple things from the same file 

  - Exporting:

    ```js
    module.exports = { isLoggedIn, logRequests };
    ```

  - Importing:
    ```js
    const { isLoggedIn, logRequests } = require("./my-file.js");
    ```




## Ironlauncher with Auth boilerplate


<!-- 

This is the command we've used so far:
"npx --yes ironlauncher library-project"

-->

- Command: `npx ironlauncher@latest just-a-demo --auth`
  - IMPORTANT: remind students to select the option "views"


- Fix: ironlauncher not installing dependencies
  - see `Express - Ironlauncher.md`




- Demo: run & explain what it has created
  - package.json
    - scripts 
    - dependencies (bcryptjs + connect-mongo + express-session)
  - /config/index.js added configuration for sessions
  - /routes/auth.js
    - signup
    - login
    - logout
      - note: it's a GET request
  - IMPORTANT: 
    - see that routes are mounted in `app.js` (ex. on top of "/auth")
    - ex. `/auth/signup`
  - /middlewares



- Students can use that to generate project2

