

# Express - GET Method - Route Params and Query String


<!-- 

Status: draft (contains all the topics to cover but would be good to improve details)


Note:
- this lesson took much longer than it seems (we also saw many examples though)
- students find it complex to understand

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
    Pizza.find({title: ""});
  ```

- Example: https://github.com/Ironmaidens-Ironhack-Jan-2022/IronmaidensCommerce/commit/b65a5d226c363c5e15acde6c69b6b5ca03d2a443





## Intro


- URL Structure: 
  https://cdn.cognitiveseo.com/blog/wp-content/uploads/2019/11/url-structure-1024x538.jpg

  - Explain `query string`

  - Path: identifies a unique resource but can also be used to send data


- 2 ways of sending data in the URL
  - QUERY PARAMS
  - ROUTE PARAMS


- Example: AirBnb


- When we use each one (typically):
  - Route params > Identify unique resources
  - Query params > Filter/Sort resources


- More Examples: 
  - Youtube
  https://www.youtube.com/c/programmingwithmosh/search?query=promises

  - Google Drive
  https://drive.google.com/drive/u/3/my-drive


- Sneak Peek: 


    ```
    router.get('/', (req, res) => {
        console.log(req.query.myquery);
    });
    ```

    ```
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


  ```javascript
    app.get("/artists/:artistName", (req, res, next) => {
        req.params.artistName
    })
  ```



  - IMPORTANT: you will receive data as a STRING
    - `req.params.productId`: will be a string


### Multiple Route Params

  https://domain.com/artists/madonna/albums/ray-of-light
  https://domain.com/artists/madonna/albums/like-a-virgin


  ```javascript
    app.get("/artists/:artistName/albums/:albumTitle", (req, res, next) => {
        req.params.artistName
        req.params.albumTitle
    })
  ```



### IMPORTANT: Common problem with params

```
app.get("/:productName", function (req, res, next) {    
    res.send("display product page..... " + req.params.productName);
});

app.get("/contact", function (req, res, next) {
    res.send("display contact page");
    // res.render("contact");
});
```

Solution: put before the routes that are more specific (and later the ones with params)




## Query String

<!--

@Luis: 

- IMPORTANT: (before this step) implement page with list of resources
  - ex. /search or /pizzas

- Functionality:
  - maxPrice
  - sortBy

-->


- One query param

  https://domain.com/artists?genre=pop

  ```javascript
    app.get("/artists", (req, res, next) => {
        req.query.genre
    })
  ```

- Multiple
  https://domain.com/artists?genre=pop&country=spain


  ```javascript
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

