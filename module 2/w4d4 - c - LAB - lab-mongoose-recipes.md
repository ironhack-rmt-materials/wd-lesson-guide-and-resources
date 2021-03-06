

# LAB - lab-mongoose-recipes

- Note: students find a bit difficult that they need to wait for the asynchronous operations (chaining promises or using async/await)

- Recommendation: solve first using promises (remind them they'll need to chain for every async operation with a .then) + then convert it to async/await (they'll find it much easier)




## Iteration 2 - Schema


- ingredients - Type Array of Strings
  
  ```
  ingredients: [String]
  ```



## Iteration 2 - Create a recipe

- The code needs to be once the connection is stablished -- inside mongoose.connect.then()


## Iteration 3

To keep chaining promises, remember to return a promise:

    ```
    .then( ()=>{
        return Recipe.create(data);
    })
    .then()
    .then()
    ```


## Iteration 4

- `Model.findOneAndUpdate()` returns original data

- You can pass a third parameter with options:

    ```
    Cat.findOneAndUpdate(condition, update, {returnOriginal: false},
    ```



## Iteration 6 - Close the Database
- Bonus
- you can use mongoose.connection.close()
- but you can only close the connection when you don't need it anymore
  - remember that requests are asynchronous so, if you just add the line to disconnect at the end of your file you will have an error
  - instead of that, you can use Promise.all();

Example:

    ```
    Promise.all([recipeUpdate, recipeRemove])
        .then(result => {
        mongoose.connection
            .close()
            .then(() => console.log(`connection closed`))
            .catch(err => console.log(`error closing connection: ${err}`));
        })
        .catch(err => console.log(`an error has occurred: ${err}`));
    })

    ```
