

# w7d3


- Ask p3 preferences (e.g. ask in the afternoon, with DL tomorrow 9am)


update:
- create model in a separate file (e.g. `Pizza.model.js`)
- (IMPORTANT) Lab "Express Mongoose Recipes": now queries to DB are inside each route 

  ```js
  app.post("/recipes", () => {
    Recipe.create()
  })
  ```




## Day planning


<!--

Demo: continue on ironRestaurant

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
    - Sample query on MongoDB
    - Today, we will start doing this things with code
  - req.params
  - req.query

- (if not done yet) Express - Route Params & Query String [1.5h]
  - GET /drinks/:drinkName (req.params)
  - GET /drinks/ + maxPrice (req.query)


- Mongoose - Introduction
  - Includes: 
    - Full CRUD (inc. req.body)
    - 2 models
    - relations and populate


- (bonus) Session with extra topics (branches, promises, copilot) [40m]
  - git branches 
  - convert promises to async/await
  - introduce other models/LLMs (e.g. Claude)
  - show also how we can use the chat from GitHub copilot ('edit' mode)
  <!--
    Note:
    - this session can also be done as a recording
    - recording in Spanish from sept 25: https://www.loom.com/share/0c1ad7f0ed1345619d138a16fdf3014b?sid=6fa72632-a124-4f65-ab40-12a0082b1916
  -->


- Before Lunch: ask for preferences project 3
  - see `project preferences.md`
  - Deadline: Tomorrow by 10am.



Note: 
- all the part of Mongoose is usually demanding for students.
- try to ask for challenges/exercises 



## Active Learning

- (individual) LAB | Express Mongoose Recipes
  
- (in groups) Mini Project - REST API - Day 3

