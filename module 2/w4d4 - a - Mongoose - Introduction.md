

# Mongoose - Introduction


<!-- 

Methodology:
- follow lesson on students portal (~~partly highlighted~~)
- at the same time, practice all the examples with the students (eg. create a DB for sport players).

Notes:
- to start making queries to the DB with mongoose, instead of adding code inside a route (need to send http request to that route), just create a file and execute it directly with node on the CLI (but explain students that later on we will be putting our code inside routes).

-->


Summary:

- MVC pattern
  - https://media.geeksforgeeks.org/wp-content/uploads/20210629165722/mvc.png
  - https://seguridad.cicese.mx/uploads/notautic/utic23-5a3c250c42cae.png


- Example (students portal: "Example of MVC Pattern"):

  ```javascript
    router.get('/product-list', (req, res) => {
      // this CONTROLLER is...
      Product.find() // ... asking for data from the Product MODEL and ...
        .then(productsFromDB => {
          const data = { productsFromDB };
          res.render('products/list', data); //  ... sending a VIEW to the client
        })
        .catch(error => console.log(error));
    });
  ```

- ODMs (Object Document Mapper) + Mongoose
  - https://user-images.githubusercontent.com/62245004/98396310-99937000-206e-11eb-9ad1-4799d58e8699.png


- Mongoose setup



<!--
@Luis:

Instead of the steps in the students portal, do the following
  - create "mongoose-playground.js"
  - Start creating a basic Schema
      const productSchema = new Schema({});
  - Then create the model
  - Then connect to DB
  - Then Model.create()
  - Then Model.find()

-->







- Connect to DB

  <!-- @Luis: create "mongoose-playground.js" -->


  ```javascript
    const mongoose = require('mongoose');

    mongoose
      .connect('mongodb://localhost/myDataBaseName')
      .then(x => console.log(`Connected to Mongo! Database name: "${x.connections[0].name}"`))
      .catch(err => console.error('Error connecting to mongo', err));
  ```



- Creating our first model
  `const Product = mongoose.model('Product', { name: String });`


<!-- 

[IMPORTANT: skip this part (instance + save). Later we will do it in one step with Model.create())]


- Creating an instance of our model  
  `const kitty = new Cat({ name: 'Ironhacker' });`

- If we want to save it in the database...
```
  kitty
  .save()
  .then(newCat => console.log(`A new cat is created: ${newCat}!`))
  .catch(err => console.log(`Error while creating a new cat: ${err}`));
```

-->


- List all "cats"
  - `Product.find()`
  - we can use it with callbacks
  - we can use promises (explain in detail)

- Introduce `Product.create()`


- (skip) Organize code (eg. move to functions)
- (skip) Mongoose connection events
- (skip) Promises & Promise.all




Some things to mention:

- Default name for  collections:
  - "When we use the Cat model to interact with the database, it will only be interacting with a collection that shares a name with it. That collection is the cats collection."

  - Mongoose will add an "s" at the end of the 
    - Why does mongoose always add an s to the end of my collection name & how to choose different name:
      https://stackoverflow.com/a/10559895/11298742


- Mongoose 'static' methods vs. 'instance' methods
  - https://stackoverflow.com/questions/29664499/mongoose-static-methods-vs-instance-methods

  - "statics" are the methods defined on the Model. ex. `Product.find()`
  - "instance" methods are defined on the document (instance). ex. `myProduct.save()`

