

# Express - Dynamic Views


<!-- Status: draft -->



## Intro

- Today we will learn how to organize & reuse our html code




- (Optional) Ask students how we want to call our pizzas:
  - https://pixabay.com/photos/pizza-plate-food-cheese-lunch-3010062/
    - margarita
  - https://pixabay.com/photos/pizza-italian-homemade-cheese-3007395/
    - veggie
  - https://pixabay.com/photos/pizza-italian-pasta-food-cheese-5179939/
    - seafood



## First step


Task:

- Make sure you're running the project from yesterday
  - `nodemon app.js`

- Create 3 routes (one for each pizza)
- For each route, just do `response.send()` with a short message
  - /pizzas/margherita --> response.send("page for margherita")
  - /pizzas/carbonara --> response.send("page for carbonara")
  - /pizzas/funghi --> response.send("page for funghi")

Time: 5-10min.



## Second step

- Create 3 html files (one for each product)
  <!-- Only LT (ask students to skip this step) -->

- Add a navbar

- Explain why this is not ideal (DRY)

- Solution:
  - We will use a template engine (handlebars)


- Handlebars Summary:
  - Reuse code for all pages (ex. navigation menu, footer...)  → Layout
  - Reuse code for pages of the same type (ex. product pages, course pages)  → Views
  - Reuse code inside your views  → Partials



## Handlebars

- Handlebars:
  - https://handlebarsjs.com/
  - JavaScript library for building templates 
  - based on the Mustache Templating Language

- Advantage: "we can make templates dynamic"


## Basic Setup

- Package: https://www.npmjs.com/package/hbs

- Install hbs

    `$ npm install hbs`

- Config Express

    ```js
    app.set("views", __dirname + "/views"); //tells our Express app where to look for our views
    app.set("view engine", "hbs"); //sets HBS as the template engine
    ```



- Create a view (ex. `views/product.hbs`)

  <!-- - @Luis: do layout first? Nope, we need to do res.render() first -->


- Render a view

    ```javascript
    app.get("/", (req, res, next) => res.render("product"));
    ```



## Passing info to Handlebars


- res.render() method can take an additional parameter that will contain a JavaScript object with information we can use in the view


    ```javascript
      app.get("/", (req, res, next) => {
        const data = {
            title: "Pizza Margherita",
            price: 8,
            imgFile: "pizza-margherita.jpg",
            ingredients: ["mozzarella", "tomato sauce", "basilicum"]
        }

        res.render("index", data);
      });

    ```


    ```hbs
      <h1>Title {{title}}</h1>
      <p>Price {{price}}</p>
    ```



TASK:
- Add images for our 3 pizzas
- You can use these:
  - https://pixabay.com/photos/pizza-plate-food-cheese-lunch-3010062/
  - https://pixabay.com/photos/pizza-italian-homemade-cheese-3007395/
  - https://pixabay.com/photos/pizza-italian-pasta-food-cheese-5179939/

- Time: 12min




## (skip) Escaping HTML

- We can send HTML to the view
  - Scape with `{{{ }}}`




## Built-in Helpers

- `if` block helper
  - render a block conditionally

- What is falsy in handlebars:
  > if its argument returns false, undefined, null, "", 0, or [], Handlebars will not render the block.


    ```hbs
      {{#if price}}
        <p>Price {{price}}</p>
      {{/if}}
    ```

    ```hbs
      {{#if price}}
        <p>Price {{price}}</p>
      {{else}}
        <p>Price upon request</p>
      {{/if}}
    ```


- (skip) `unless` block helper
  - It will render the block if the expression returns a falsy value.



- `each` block helper
  - iterate through arrays/objects 
  - this: `{{this}}`
  - @index
  - @key
  - @first - @last
  - note: access variables from above: `../`


  - `each` Example 1: with an array of strings
    
    ```js
      const data = {
        ingredients = ["mozzarella", "tomato sauce", "basilicum"]
      }
    ```

    ```hbs
    <ul>
      {{#each ingredients}}
        <li>{{this}}</li>
      {{/each}}
    </ul>
    ```



  - `each` Example 2: with an array of objects

    - Goal: display a list of all pizzas (title + price + link) in the homepage

    ```js
        const allPizzas = [
            {
                title: "Pizza Margarita",
                price: 12
            },
            {
                title: "Veggie Pizza",
                price: 15
            },
            {
                title: "Seafood Pizza",
                price: 20
            }
        ];

        res.render("home", {allPizzas})
    ```


    ```hbs
    {{#each pizzasArr}}
        <section>
            <h2>{{this.title}}</h2>
            <h3>Price: {{this.price}}€</h3>
        </section>
    {{/each}}
    ```




- (skip) `with` block helper


- (bonus) `log` helper (useful for debugging)

  ```hbs
    {{log "hello world"}}
  ```

  ```hbs
    {{log ingredients}}
  ```



