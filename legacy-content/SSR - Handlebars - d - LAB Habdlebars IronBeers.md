

# LAB Handlebars IronBeers


LAB URL:
- https://github.com/ironhack-labs/lab-ironbeers


<!-- 

Concepts: 
- API (we will interact through an npm package)
- Handlebars
- Promises

-->


- SETUP:
  - `nodemon app.js`
  - if you have other project running on port 3000, it will not work.
  - option 1: kill process
  - option 2: run in a different port (ex. 3001)




- Getting information from an API
  - We can use .fetch(), axios()...
  - We can use a Package that gets info from an API (as we do in this lab)
    - Note: the methods we will use are in the instructions but they can also check the documentation of the package.





- IMPORTANT (1): creating routes + rendering a view

  ```js
    app.get('/beers', (req, res) => {
      res.render('beers');
    });
  ```

  - REMEMBER: in the route we start with `/` but in res.render, we don't have `/`


- IMPORTANT (2): if you don't know the information you receive, just console.log the result you get in the promise.


  ```js
    punkAPI
      .getBeers()
      .then(beersFromApi => console.log(beersFromApi))
      .catch()
  ```

  - You may want to check the details of only one element....

  ```js
    console.log(beersFromApi[0])
    console.log(beersFromApi[0].ingredients)
  ```

  - Example: getRandom() returns an array of length 1 with a random beer (an array with an object, not directly an object)
    


- IMPORTANT (3): sending information to the view

  ```js
    app.get('/beers', (req, res) => {
      
      punkAPI
        .getBeers()
        .then(beersFromApi => {

          const myObj = {
            beersArr: beersFromApi
          }

          res.render('beers', myObj);
        })
        .catch(error => console.log(error));

    });
  ```

- IMPORTANT (4): receiving information in the view (hbs)

  ```hbs
  <h1>{{title}}</h1>

  {{#each beers}}
      {{this.title}}
      {{this.price}}
  {{/each}}
  ```

  Note: you would be iterating through an array of objects.


- IMPORTANT (5): Make sure you wait for the promise....

  ```js
    app.get('/beers', (req, res) => {
      
      punkAPI
        .getBeers()
        .then(beersFromApi => console.log('Beers from database:', beersFromApi))
        .catch(error => console.log(error));
      
      res.render('beers', beersFromApi);  // WILL NOT WORK  !!

    });
  ```



- FINALLY: 
  - focus on functionality (routes, handlebars, promises)
  - css is not the priority. If you want to do it, do it at the end.
