

# Mongoose - Introduction


<!-- 


@to-do: 
- improve these notes
- create slides (mongoose intro)


-->




## (skip) MVC pattern
  - https://media.geeksforgeeks.org/wp-content/uploads/20210629165722/mvc.png
  - https://seguridad.cicese.mx/uploads/notautic/utic23-5a3c250c42cae.png


- Example (students portal: "Example of MVC Pattern"):

  ```js
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
  

## ODMs (Object Document Mapper) + Mongoose


Diagram MERN (including Mongoose):
- https://user-images.githubusercontent.com/62245004/98396310-99937000-206e-11eb-9ad1-4799d58e8699.png



## Mongoose setup

`npm install mongoose`



<!--
@Luis:

Instead of the steps in the students portal, do the following
  - Start creating a basic Schema
      const productSchema = new Schema({});
  - Then create the model
  - Then Model.create()
  - Then Model.find()

-->


## Create a file to practice Mongoose

- `mongoose-playground.js`
- explain: in the following days, we'll have the queries in our routes
- why we use a file (and not routes): easier to test (we don't need to keep sending requests)



## Connect to DB


  ```js
    const mongoose = require('mongoose');

    mongoose
      .connect("mongodb://127.0.0.1:27017/myDataBaseName")
      .then((response) => {
        console.log(`Connected! Database Name: "${response.connections[0].name}"`);
      })
      .catch((err) => console.error("Error connecting to Mongo", err));

  ```

IMPORTANT:
- all code that we'll produce now will go inside the .then() (once we're connected to the DB)





## Schema:


```js

  const { mongoose, Schema } = require("mongoose");

  //...

  //create Schema
  const pizzaSchema = new Schema({
    title: String,
  }); 
```


## Model:


```js
  //create Model
  const Pizza = mongoose.model("Pizza", pizzaSchema);
```




## (skip) instance + save.

  ```js
    const kitty = new Cat({ name: 'Ironhacker' });

    kitty
    .save()
    .then(newCat => console.log(`A new cat is created: ${newCat}!`))
    .catch(err => console.log(`Error while creating a new cat: ${err}`));
  ```



## Create a document


Step 1: just title

  ```js
    //create a new document (a new pizza)
    Pizza.create({ title: "margarita" });
  ```

  <!-- @Luis: for title, use "margarita" instead of "pizza margarita". -->


  - Note: a new document will be created every time we execute our file.



Step 2: in a separate object


  ```js
      const pizza2 = {
        title: "veggie",
    }
  ```

  <!-- ```js
      const data = {
        title: "margarita",
        price: 8,
        imageFile: "pizza-margarita.jpg",
        ingredients: ["mozzarella", "tomato sauce", "basilicum"]
    }
  ``` -->

  - IMPORTANT: 
    - for `title`, store only a word (`margarita` instead of `pizza margarita`)
    - will make our live much easier if we then implement as a query to DB.


Step 3: display confirmation

  ```js
  Pizza.create()
    .then()
    .catch()
  ```





 ## Some other methods


- `Pizza.insertMany()` (optional) 


- `Pizza.find()`
  - we can use it with callbacks
  - we can use promises (explain in detail)




- (skip) Organize code (eg. move to functions)


- (brief) Mongoose connection events


- (brief) Promises & Promise.all
  - Mention/Refresh: promises (they will need them for today's lab)




## FAQs

Some things to mention:

- Default name for  collections:
  - "When we use the Cat model to interact with the database, it will only be interacting with a collection that shares a name with it. That collection is the cats collection."

  - Mongoose will add an "s" at the end of the 
    - Why does mongoose always add an s to the end of my collection name & how to choose different name:
      https://stackoverflow.com/a/10559895/11298742


- Mongoose 'static' methods vs. 'instance' methods
  - https://stackoverflow.com/questions/29664499/mongoose-static-methods-vs-instance-methods

  - "statics" are the methods defined on the Model. ex. `Pizza.find()`
  - "instance" methods are defined on the document (instance). ex. `myPizza.save()`


