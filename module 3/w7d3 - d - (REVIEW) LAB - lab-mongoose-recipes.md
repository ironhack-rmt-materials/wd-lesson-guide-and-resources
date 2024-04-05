

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




## Iteration 3



To keep chaining promises, remember to return a promise:

  ```js
  .then( ()=>{
      return Recipe.create(data);
  })
  .then()
  .then()
  ```



## Iteration 6

    ```js
    Cat.findByIdAndUpdate(id, update, { new: true })
    ```






