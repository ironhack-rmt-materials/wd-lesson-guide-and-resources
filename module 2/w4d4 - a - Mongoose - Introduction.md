

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


  - see sample route (students portal "Example of MVC Pattern")



- ODMs (Object Document Mapper) + Mongoose
  - https://user-images.githubusercontent.com/62245004/98396310-99937000-206e-11eb-9ad1-4799d58e8699.png


- Mongoose setup
- Connect to DB
- Creating our first model
  `const Cat = mongoose.model('Cat', { name: String });`


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
  `Cat.find()` + callback or .then()

- Organize code (eg. move to functions)
- Mongoose connection events
- Promises & Promise.all





Some IMPORTANT concepts to cover/mention in this lesson:

- Default name for  collections:
  - "When we use the Cat model to interact with the database, it will only be interacting with a collection that shares a name with it. That collection is the cats collection."

  - Mongoose will add an "s" at the end of the 
    - Why does mongoose always add an s to the end of my collection name & how to choose different name:
      https://stackoverflow.com/a/10559895/11298742



- Mongoose 'static' methods vs. 'instance' methods
  - https://stackoverflow.com/questions/29664499/mongoose-static-methods-vs-instance-methods

  - "statics" are the methods defined on the Model. ex. `Unicorn.find()`
  - "instance" methods are defined on the document (instance). ex. `Unicorn.save()`

