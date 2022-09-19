

# What is an API?


<!-- Status: draft -->


## Topics


- HTTP (refresh)


- HTTP headers
  > HTTP headers let the client and the server pass additional information with an HTTP request or response.

  - See MDN: https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers

  - Examples:
    - User-Agent (Identify the user agent / browser)
    - Set-Cookie
    - Content-Type (Indicates the media type of the resource.)


- Content Types

  > "What if we wanted to request some data from a website across the internet and then do something programmatic with that data?"


- JSON

  - Main differences between JSON and JS objects:
    - JSON: property names must be in quotes
    - JSON: double quotes (js objects can use single quotes)
    - JSON: cannot store the following data types: functions, date, undefined


- APIs 
  - explain concept of API
  - examples: 
    - twitter
    - spotify
    - Fake apis (http://jsonplaceholder.typicode.com/)


- Lab of Today
  - Punk API
    - GET https://api.punkapi.com/v2/beers/
    - GET https://api.punkapi.com/v2/beers/1
  - Note: we will use a package to interact with the API
  - The package returns a promise.

    <!-- 
      @Luis: 
      - quick refresh promises (the package returns a promise)
    -->

    ```javascript
      app.get('/beers', (req, res) => {
        
        punkAPI
          .getBeers()
          .then(beersFromApi => console.log('Beers from database:', beersFromApi))
          .catch(error => console.log(error));
        
        res.render('beers', beersFromApi);  // WILL NOT WORK  !!

      });
    ```

