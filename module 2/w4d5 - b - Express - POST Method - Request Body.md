

# Express - POST Method - Request Body


<!-- 

Status: just a summary

-->


Summary of the main topics:

- Form with POST

  ```hbs
  <form action="/login" method="POST">
      <h3>Login</h3>

      <label>
          Email:
          <input type="email" name="email" />
      </label>

      <label>
          Password:
          <input type="password" name="pw" />
      </label>

      <button type="submit">Login</button>

  </form>
  ```

- see: data is not sent in the URL
- see: dev tools - data sent in the payload

- How to access the information in a POST request
  - Configure bodyParser (no need to install since it comes with Express)

      ```js
      const bodyParser = require('body-parser');
      app.use(bodyParser.urlencoded({ extended: true }));
      ```

    <!-- note: ironlauncher will add this configuration for us -->
   
  - Read info from `req.body`


- Extra: `.env` file (used in today's lab)
  - how to create it
  - what is a ".env" file


- Middleware
  - introduce the concept of middleware
    - https://expressjs.com/en/guide/using-middleware.html
    - https://res.cloudinary.com/practicaldev/image/fetch/s--PHYkGiKU--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/73eusy0bc095c9w8tstw.png
    - https://d33wubrfki0l68.cloudfront.net/a22bb45df146d43b57f2f6c90182d19e7394cd96/d6e10/assets-jekyll/blog/express-middleware-examples/middleware-30b3b30ad54e21d8281719042860f3edd9fb1f40f93150233a08165d908f4631.png


