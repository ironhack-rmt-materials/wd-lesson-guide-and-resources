

# LAB - IronBeers

<!-- 

Concepts: 
- API (we will interact through an npm package)
- Handlebars
- Promises

-->



- Getting information from an API
  - We can use .fetch(), axios()...
  - We can use a Package that gets info from an API (as we do in this lab)
    - the methods we will use are in the instructions but they can also check the documentation





- IMPORTANT (1): creating routes + rendering a view

  - in the route we start with "/" but in res.render, we don't have "/"

  ```
  app.get('/beers', (req, res) => {
    res.render('beers');
  });
  ```



- IMPORTANT (2): if you don't know the information you receive, just console.log the result you get in the promise.


  ```
    punkAPI
      .getBeers()
      .then(beersFromApi => console.log(beersFromApi))
      .catch()
  ```

  - You may want to check the details of only one element....

  ```
  console.log(beersFromApi[0])
  ```



- IMPORTANT (3): Make sure you wait for the promise....

  ```
  app.get('/beers', (req, res) => {
    
    punkAPI
      .getBeers()
      .then(beersFromApi => console.log('Beers from database:', beersFromApi))
      .catch(error => console.log(error));
    
    res.render('beers', beersFromApi);  // WILL NOT WORK  !!

  });
  ```



