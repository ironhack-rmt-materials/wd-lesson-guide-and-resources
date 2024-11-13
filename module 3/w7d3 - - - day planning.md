

# w7d3


- Ask p3 preferences (ex. ask in the afternoon, with DL tomorrow 9am)


update:
- create model in a separate file (ex. Pizza.model.js)
- LAB "Express Mongoose Recipes" now queries to DB are inside each route (IMPORTANT)

  ```js
  app.post("/recipes", () => {
    Recipe.create()
  })
  ```




## Day planning



<!--


Demo: continue on ironRestaurant / create new app as in students portal ?
- if we follow students portal (books)
  - it's easier for them the "research" part
  - it also helps if we do a quick refresh on relationships w7d4
- if I use restaurant, it's an additional example BUT the code from w7d1 is res.send and res.sendFile



Notes: 
- create a separate file to practice mongoose methods ("mongoose-playground.js")
- use just res.json + test with Postman
- contents in the students portal for req.params and req.query are completely new (no DB yet)
  - form: instead of form, use Postman ??


- DATA MODELS: the part of data models can also be explained based on this project, eg:
  - Product model & Reviews as nested document
  - Product model & Seller model

-->


- LAB Q&A 

- (Quick) Refresh
  - MongoDB (database, collection, document, field)
  - Sample query
  - Today, we will start doing this things with code

- Express - Route Params & Query String [1.5h]
  - GET /drinks/:drinkName (req.params)
  - GET /drinks/ + maxPrice (req.query)
  - POST /drinks/ (req.body)

- Mongoose - Introduction

- Before Lunch: ask for preferences project 3
  - see `project preferences.md`
  - Deadline: Tomorrow by 10am.



Note: 
- all the part of Mongoose is usually demanding for students.
- try to ask for challenges/exercises 



## Active Learning

- (individual) LAB | Express Mongoose Recipes
  
- (in groups) Mini Project - REST API - Day 3


