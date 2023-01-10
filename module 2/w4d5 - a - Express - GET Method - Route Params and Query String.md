

# Express - GET Method - Route Params and Query String


<!-- 

Status: draft (contains all the topics to cover but would be good to improve details)


Note:
- this lesson took much longer than it seems (we also saw many examples)
- students find it complex to understand.

Suggested approach: 
- show theory first:
  -- url structure 
  -- different ways to pass info (path, query string, body of post request)
  -- syntax to receive information for each of them

- once they've been exposed to the theory, codealong different examples
  -- include forms (needed for lab 'express spotify')
  -- codealong: e-commerce OR music app OR airbnb clone




- Basic exercise to refresh Express GET & POST:
  https://github.com/Ironhack-Team-Triangle-July2021/express-get-and-post-exercise

  Bonuses (for students that finish):
  - allow to filter by price also /products/categoryName
  - style
  - get the array of products from an external API (eg. https://github.com/public-apis/public-apis#shopping)

-->


## Step Zero

- In the app from yesterday, we can replace the static objects with a query to the DB (allows to refresh + it will make code easier to follow when we do route params)

- INSTEAD OF:

  ```js
      const data = {
          title: "Pizza Margherita",
          price: 8,
          imgFile: "pizza-margherita.jpg",
          ingredients: ["mozzarella", "tomato sauce", "basilicum"]
      }

      res.render("pizza-page", data);
  ```

- DO:
  ```js
    Pizza.findOne({title: ""});
  ```

- Example: https://github.com/Ironmaidens-Ironhack-Jan-2022/IronmaidensCommerce/commit/b65a5d226c363c5e15acde6c69b6b5ca03d2a443


TASK:
- modify the other pizza routes:
    - app.get("/pizzas/veggie",
    - app.get("/pizzas/seafood"
- instead of creating an object, now we want to get the info from the DB
Time: 10min.




## Intro


- Slides (Route params vs. query string vs. request body): 
  https://docs.google.com/presentation/d/1Z-f8heYSALVVuaevvMBcsE5OvOH1rSvyhkZXgY-JXW4/edit?usp=sharing



- When we use each one (typically):
  - Route params > Identify unique resources
  - Query params > Filter/Sort resources


- Examples: 
  - AirBnb

  - Youtube
  https://www.youtube.com/c/programmingwithmosh/search?query=promises

  - Google Drive
  https://drive.google.com/drive/u/3/my-drive



- Sneak Peek: 


    ```js
    router.get('/', (req, res) => {
        console.log(req.query.myquery);
    });
    ```

    ```js
    router.get('/:user', (req, res) => {
        console.log(req.params.user);
    });

    ```


## Route Params

- Basic Route Params

  https://domain.com/artists/5
  https://domain.com/artists/7
  https://domain.com/artists/849


  https://domain.com/artists/madonna
  https://domain.com/artists/britney
  https://domain.com/artists/daddy-yankee


  ```js
    app.get("/artists/:artistName", (req, res, next) => {
        req.params.artistName
    })
  ```



  - IMPORTANT: you will receive data as a STRING
    - `req.params.productId`: will be a string


### Multiple Route Params

  https://domain.com/artists/madonna/albums/ray-of-light
  https://domain.com/artists/madonna/albums/like-a-virgin


  ```js
    app.get("/artists/:artistName/albums/:albumTitle", (req, res, next) => {
        req.params.artistName
        req.params.albumTitle
    })
  ```



### IMPORTANT: Common problem with params


Example 1:

  ```js
  app.get("/pizzas/:pizzaName", function (req, res, next) {    
      //...
  });

  app.get("/pizzas/create-your-own-pizza", function (req, res, next) {
      //...
  });
  ```

Example 2:

  ```js
  app.get("/:productName", function (req, res, next) {    
      res.send("display product page..... " + req.params.productName);
  });

  app.get("/contact", function (req, res, next) {
      res.send("display contact page");
      // res.render("contact");
  });
  ```

Solution: put before the routes that are more specific (and later the ones with params)




## BEFORE Query String

<!--

@Luis: 

- IMPORTANT: (before this step) implement page with list of resources
  - ex. /search or /pizzas

-->

- Give students this view `product-list.hbs`:

  ```hbs
  <h1>List of pizzas in our DB:</h1>

  {{#each pizzasArr}}
      <section class="pizza-summary">
          <h2>{{this.title}}</h2>
          <h3>Price: {{this.price}}€</h3>

          <hr>
      </section>
  {{/each}}
  ```

TASK:
- implement a new route `GET /pizzas`
- Inside this route:
  - Send a query to get all the pizzas in our DB
  - Once we have the result, render the view `product-list.hbs`
    - Note: the view expects to receive an array with the name `pizzasArr`
- (Bonus 1): modify the view, including a link for each pizza
- (Bonus 2): add some css

Time: 10min.



## Query String

<!--

- Functionality:
  - maxPrice
  - sortBy

- maxPrice: convert to a number:

    let {maxPrice} = req.query;
    maxPrice = Number(maxPrice);

-->


- One query param

  https://domain.com/artists?genre=pop

  ```js
    app.get("/artists", (req, res, next) => {
        req.query.genre
    })
  ```

- Multiple
  https://domain.com/artists?genre=pop&country=spain


  ```js
    app.get("/artists", (req, res, next) => {
        req.query.genre
        req.query.country
    })
  ```



## Route Params vs. Query Strings



## Query String from Forms

- `<form action="/search" method="GET">`


Things to mention:
- action
- method (GET / POST)
- input fields
  - types of inputs (text, number, password, email...)
  - name
- button `<button type="submit">`

