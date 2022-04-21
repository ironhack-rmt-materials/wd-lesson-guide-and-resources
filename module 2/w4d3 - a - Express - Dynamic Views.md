

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




## Basic Setup

- Install hbs

    `$ npm install hbs`

- Config Express

    ```
    app.set("views", __dirname + "/views"); //tells our Express app where to look for our views
    app.set("view engine", "hbs"); //sets HBS as the template engine
    ```


- Create a view (ex. `views/product.hbs`)


- Render a view

    ```
    app.get("/", (req, res, next) => res.render("product"));
    ```



## Handlebars

- Handlebars.js is the JavaScript library for building clean logic-less templates based on the Mustache Templating Language.
    - "Templating Language"

- Advantage: "we can make templates dynamic"


- res.render() method can take an additional parameter that will contain a JavaScript object with information we can use in the view


    ```
    app.get("/", (req, res, next) => {
    let data = {
        name: "Ironhacker",
        bootcamp: "Ironhack Web Dev"
    };

    res.render("index", data);
    });

    ```


    ```
    <h1>Hello {{name}}!</h1>
    <p>Welcome to the {{bootcamp}}!!</p>
    ```



## (Bonus) Escaping HTML

- We can send HTML to the view
  - Scape with {{{ }}}



## Built-in Helpers

- `if` block helper
  - render a block conditionally
  - if its argument returns false, undefined, null, "", 0, or [], Handlebars will not render the block.

    ```
    {{#if age}}
        <p>Age: {age}</p>
    {{/if}}
    ```

    ```
    {{#if firstName}}
        {{firstName}}
    {{else}}
        Info not available
    {{/if}}
    ```


- (bonus) `unless` block helper
  - It will render the block if the expression returns a falsy value.


- `each` block helper
  - iterate through arrays/objects
  - @index
  - @key
  - @first - @last


- (bonus) `with` block helper

