

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
- use just res.json + test with Postman

-->


- LAB Q&A 

- (Quick) Refresh
  - MongoDB (database, collection, document, field)
    - Sample query on MongoDB
    - Today, we will start interacting with the DB with code
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
    - cheatsheet git branches: https://gist.github.com/luisjunco/d9d0a7d62e7633568533b7214f6af840
  -->


- Before Lunch: ask for preferences project 3
  - see `project preferences.md`
  - Deadline: Tomorrow by 10am.



Note: 
- all the part of Mongoose is usually demanding for students.
- try to include challenges/exercises 



## Active Learning

- (individual) LAB | Express Mongoose Recipes
  
- (in groups) Mini Project - REST API - Day 3

