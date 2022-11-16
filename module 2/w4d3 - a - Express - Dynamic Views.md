

# Express - Dynamic Views


<!-- Status: draft -->



## Intro



- Goal of our codealong:  e-commerce website with,

    - home
    - contact
    - 3 products (1 page per product)
      - title
      - price
      - image



- Handlebars Summary:
  - Reuse code for all pages (ex. navigation menu, footer...) -> layout
  - Reuse code for pages of the same type (ex. product pages, course pages) -> views
  - Reuse code inside your views -> partials




## First step


Task:

- Create 3 routes (one for each pizza)
- For each route, just do `response.send()` with a short message
  - /pizzas/margherita --> response.send("page for margherita")
  - /pizzas/carbonara --> response.send("page for carbonara")
  - /pizzas/funghi --> response.send("page for funghi")


## Second step

- Create 3 html files (one for each product)
  <!-- Only LT (ask students to skip this step) -->

- Add a navbar


- Explain why this is not ideal (DRY)

- Solution:
  - We will use a template engine (handlebars)

- Handlebars:
  - Reuse code for all pages → Layout
  - Reuse code for pages of the same type → Views
  - Reuse code inside your views → Partials




## Basic Setup

- Install hbs

    `$ npm install hbs`

- Config Express

    ```javascript
    app.set("views", __dirname + "/views"); //tells our Express app where to look for our views
    app.set("view engine", "hbs"); //sets HBS as the template engine
    ```



- Create a view (ex. `views/product.hbs`)
  - @Luis: do layout first? Nope, we need to do res.render() first


- Render a view

    ```javascript
    app.get("/", (req, res, next) => res.render("product"));
    ```



## Handlebars

- Handlebars:
  - JavaScript library for building templates 
  - based on the Mustache Templating Language

- Advantage: "we can make templates dynamic"


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

  <!--
  @Luis: Image files
    https://github.com/ironicHackers-Ironhack-Sept-22/ecommerce-ironic-pizzas/tree/main/public/images
  -->


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


- (bonus) `unless` block helper
  - It will render the block if the expression returns a falsy value.


- `each` block helper
  - iterate through arrays/objects 
  - example: array of ingredients
  - `{{this}}`
  - @index
  - @key
  - @first - @last
  - note: access variables from above: `../`


- (bonus) `with` block helper

