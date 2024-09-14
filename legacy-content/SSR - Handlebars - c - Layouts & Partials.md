
# Express - Layouts & Partials


<!-- 

- Notes:
  - Partials take quite a bit to explain if we do codealong (just mention them)

-->


## Intro

Layout: reuse code for all pages (ex. navigation menu, footer...).
- example: add a navigation menu at the top of all pages



## Layouts


- create `layout.hbs`
- add html
- inside layout.hbs, add `{{{ body }}}`
  
  - IMPORTANT: notice the "TRIPLE" curly brace

    ```hbs
      <!DOCTYPE html>
      <html lang="en">
      <head>
      </head>

      <body>

          {{{ body }}}

      </body>
      </html>
    ```


## (Extra) Reading data from layout

Example:

  ```js
    app.get("/contact", (request, response, next) => {

        const data = {
            loadCoolCss: true
        }

        response.render("contact-page", data);
    });
  ```


## (skip) Skipping layouts

- Set `layout: false` in the object we pass to the view

    ```js
    app.get("/teams", (req, res, next) => {
        const data = {
            layout: false
        }
        res.render("teams", data);
    });
    ```



## Partials (Bonus / Self guided / Demo)

<!--
@LT:
- do a quick demo (not codealong)
-->


- Configure 

  ```js
    const hbs = require("hbs");

    // ...

    hbs.registerPartials(__dirname + "/views/partials"); //tell HBS which directory we use for partials
  ```


- Create a Partial (ex. banner / list with other products / contact form)

  ```hbs
    <div class="banner">
      <h3>Order now</h3>

      <a href="mailto:iron@ironhack.com">iron@ironhack.com</a>
    </div>
  ```

- Filename: `ctaOrderNow.hbs`


- Call a Partial from a View

  ```hbs
    {{> myPartial }}
  ```

- Note: 
  - use `camelCase.hbs` for names of partials (`kebab-case.hbs` will not work)


  <!-- IMPORTANT: nodemon may not listen to changes on partials (may need to restart) -->

- Note:

  In the partial, we can access data from the view that renders the partial.
  (Example, if we want to display "Order your Pizza Margarita")

  ```hbs
    {{> ctaOrderNow}}
  ```
  ```hbs
    {{title}}
  ```


- Passing parameters to partials


  ```hbs
    {{#each players}} 
      {{> playerCard this}} 
    {{/each}}
  ```



## (Bonus) List of pizzas

Create a route `GET /pizzas` to display a full list of pizzas.


  ```js
  app.get("/pizzas", (req, res, next) => {

      const pizzasArr = [
          {
            title: 'Pizza Margarita',
            price: 12,
            imageFile: 'pizza-margarita.jpg',
          },
          {
              title: "Veggie Pizza",
              price: 15,
              imageFile: "pizza-veggie.jpg"
          }, 
          {
              title: "Seafood Pizza",
              imageFile: "pizza-seafood.jpg"
          }
      ];

      const data = {
          pizzasArr: pizzasArr
      }

      res.render("product-list", data)

  })
  ```



  ```hbs

  {{#each pizzasArr}}
      <section>
          <h2>{{this.title}}</h2>
          <h3>Price: {{this.price}}€</h3>
      </section>
  {{/each}}

  ```


## Summary

Reuse code for all pages → Layout
Reuse code for pages of the same type → Views
Reuse code inside your views → Partials

