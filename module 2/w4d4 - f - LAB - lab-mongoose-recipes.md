

# LAB - lab-mongoose-recipes

- Note: students find a bit difficult that they need to wait for the asynchronous operations (chaining promises or using async/await)

- Recommendation: 
  - solve first using promises with `.then()` (remind them they'll need to chain for every async operation with a .then)
  - then convert it to `async/await` (they may find it much easier, remind to use try/catch)

- Bonus:
  - different patterns for promises (then/catch, async/await)




## Iteration 1 - Recipe Schema

- Model is defined in a specific file `/models/Recipe.model.js`



## Iteration 2 - Schema


- ingredients - Type Array of Strings
  
  ```js
  ingredients: [String]
  ```



## Iteration 2 - Create a recipe

- The code needs to be once the connection is stablished
    - Make sure it is inside the `.then` in `mongoose.connect.then()`



## Iteration 3


<!-- IMPORTANT -->
<!-- Note: this require is already in the initial code  -->
<!-- IMPORTANT -->

- Import json file:

  ```js
    const data = require('./data'); //Import of the data from './data.json'
  ```



To keep chaining promises, remember to return a promise:

  ```js
  .then( ()=>{
      return Recipe.create(data);
  })
  .then()
  .then()
  ```


## Iteration 4

- `Model.findOneAndUpdate()` returns original data

- You can pass a third parameter with options:

    ```js
    Cat.findOneAndUpdate(condition, update, { returnDocument: 'after' })
    ```



## Iteration 6 - Close the Database

Bonus.

Why closing the connection: 
- good practice (detailed explanation https://stackoverflow.com/a/4111628/11298742)

How: 
- you can use `mongoose.connection.close()`
- but you can only close the connection when you don't need it anymore
  - remember that requests are asynchronous so, if you just add the line to disconnect at the end of your file you will have an error
  - instead of that, you can use Promise.all();


Example:

  ```js
  Promise.all([recipeUpdate, recipeRemove])
      .then(result => {
          mongoose.connection
              .close()
              .then(() => console.log(`connection closed`))
              .catch(err => console.log(`error closing connection: ${err}`));
      })
      .catch(err => console.log(`an error has occurred: ${err}`));
  ```



