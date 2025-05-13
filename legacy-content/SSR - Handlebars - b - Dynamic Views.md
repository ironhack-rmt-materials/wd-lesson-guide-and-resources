

# Express - Dynamic Views


<!-- Status: complete -->



## Intro

- Today we will learn how to organize & reuse our html code



## Exercise: Initial setup + adding new routes

0. In case you don't have the app from yesterday:
- `REPO_URL`
- (fork)
- clone
- npm install


1. Make sure you're running the project from yesterday: `nodemon app.js`

2. Create 3 routes (one for each pizza):
  - /pizzas/margarita → response.send("page for margarita")
  - /pizzas/veggie → response.send("page for veggie")
  - /pizzas/seafood → response.send("page for seafood")

Notes:
- IMPORTANT: for each route, just do `response.send()` with a short message.
- Test in the browser (make sure you can see all 3 pages)

Bonus: 
- research/practice "js rest parameters"

Time: 15min.



(After exercise):
- Add/update Navbar


(break)

<!-- @LT: can use the break to do the next step -->


## Second step

- Create 3 html files (one for each product)
  - title
  - price
  <!-- Only LT (ask students to skip this step) -->

- Explain why this is not ideal (DRY)

- Solution:
  - We will use a template engine (handlebars)
  - Logo: https://user-images.githubusercontent.com/23629340/34818880-6dab9b04-f6bc-11e7-8719-99981c59d03a.png


- Handlebars Summary:
  - Reuse code for all pages (e.g. navigation menu, footer...)  → Layout
  - Reuse code for pages of the same type (e.g. product pages, course pages)  → Views
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



- Create a view (e.g. `views/product.hbs`)

  <!-- - @LT: do layout first? Nope, we need to do res.render() first -->


- Render a view

    ```js
    app.get("/", (req, res, next) => res.render("product"));
    ```

  <!--

    UPDATE: use this syntax

    res.render("product.hbs");
    res.render("./subdirectory/product.hbs");

  -->


## Passing info to Handlebars


- res.render() method can take an additional parameter that will contain a JavaScript object with information we can use in the view

  <!-- 
  
  @LT: 
  - for now, show only with 1 property (title) 
  - in the exercise below, we will do title + price
  -->

    ```js
      app.get("/pizzas/margarita", (req, res, next) => {
        res.render("product", {title: "margarita"});
      });

    ```

    ```hbs
      <h1>Pizza {{title}}</h1>
    ```



Explain: some possible patterns

  - passing an object directly

    ```js
      app.get("/pizzas/margarita", (req, res, next) => {
        res.render("product", {title: "margarita"});
      });
    ```

  - variable with an object

    ```js
      app.get("/pizzas/margarita", (req, res, next) => {

        const data = {
          title: "margarita"
        };

        res.render("product", data);
      });
    ```

  - Note: usually, this info will come from the DB.


## Practice: passing info to Handlebars

- Iteration 1:
  - For each pizza, display `title` + `price`
  - You can use data from here: https://stackblitz.com/edit/js-bzqmw5?file=index.js


- Bonus:
  - Add images for our 3 pizzas
  - You can use these:
    - https://pixabay.com/photos/pizza-plate-food-cheese-lunch-3010062/
    - https://pixabay.com/photos/pizza-italian-homemade-cheese-3007395/
    - https://pixabay.com/photos/pizza-italian-pasta-food-cheese-5179939/
  - Note: click "free download" (1280x854px is fine)


- Time: 15min

  <!-- @LT: alternative, send images on Slack -->




## (skip) Escaping HTML

- We can send HTML to the view
  - escape with `{{{ }}}`




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



  - (skip) Example 2: `each` with an array of objects

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

  > allows you to change the evaluation context


  ```hbs
      <p>{{address.street}}</p>
      <p>{{address.postcode}}</p>
  ```


  ```hbs
    {{#with address}}
      <p>{{street}}</p>
      <p>{{postcode}}</p>
    {{/with}}
  ```



- (bonus) `log` helper (useful for debugging, displayed in the CLI)

  ```hbs
    {{log "hello world"}}
  ```

  ```hbs
    {{log ingredients}}
  ```



## Extra: show how to work with an array of objects

Why: common pattern + today's lab

Data:

  ```js

  ingredients: [
    {
        ingredientName: "mozzarella",
        calories: 400
    },
    {
        ingredientName: "tomato sauce",
        calories: 200
    },
    {
        ingredientName: "basilicum",
        calories: 30
    },
  ],

  ```

View (`product.hbs`):

```hbs
  {{#each ingredients}}
    {{log this}}
  {{/each}}
```