


<!--

@todo: create gist

-->




*** GET: Route Params ***

- Example URL: https://localhost:3000/artists/madonna

- How to access route params:

app.get('/artists/:artistname/', (req, res) => {
    const artist = req.params.artistName;
});


- Note, we can also define multiple params in our routes, for example:

/:school/:class/:student

/artists/:artistname/albums/:albumName




*** GET: Query String ***

- Example URL: https://localhost:3000/search?price=200


- How to access the information from query string: we use the object `req.query`

Example:

app.get('/search', (req, res) => {
    console.log(req.query); // req.query object
    console.log(req.query.price); // price
    console.log(req.query.location); // location
});


*** POST: Request Body ***

- Data is sent in the 'body' of the http request (also called 'payload').

- To read the data, we need to configure the package `bodyParser`:

    ```
        const bodyParser = require('body-parser');
        app.use(bodyParser.urlencoded({ extended: true }));
    ```

- Then we can read data from the object `req.body`

    ```
    app.post('/login', (req, res) => {
        console.log(req.body)
        if(req.body.email === 'bob@bob.com'){
            //...
        }
    })
    ```