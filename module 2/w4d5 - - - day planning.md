
# w4d5

<!--

NOTES:
- too much workload today (students overwhelmed at the end of the day). 
- see if that can be improved.
- skip lab review & start fast.



Methodology:
- continue working on IronRestaurant
- example: https://github.com/RemoteRaccoons-Ironhack-Nov-22/ironrestaurant-pizzaForEach/



@todo:
- create a discovery-lab ???
- give an overview of the functionality we'll have at the end of the day
- explain main concepts (route params etc -- with examples coding )
- students fork + clone
- implement changes with hints
- problem: many important concepts (ex. forms, body etc)
  - for those topics, I could record short videos (so that it's all self-guided).



Friday: try to finish earlier.

-->


- Questions from lab [20min.]

- Refresh week 4 [20min.]
  - Promises
  - Node.js
  - NPM (node package manager)
  - Express.js
  - hbs (template engine)
    - views
    - layout
    - partial
  - MongoDB
  - mongoose
    - Schema + mongoose built-in validators
    - Model
    - mongoose methods


- Changes on yesterday's project (seed + get data from DB) [2h]

- get: req.params, req.query

- forms

- post: req.body





## Pass them a Seed file

- example: https://github.com/ByteWarriors-Ironhack-Feb-23/warriors-ironrestaurant/blob/main/bin/seeds2.js

    <!-- IMPORTANT: change DB name -->
    <!-- IMPORTANT: seeds.js not valid, seeds2.js is the correct one -->

    <!-- @Luis: 
         - update seeds file so that ingredients is an array of objects
         - (so that the view from yesterday keeps working)     
    -->


Exercise: Initial setup & warmup

- Iteration 1: make sure you're running the project from yesterday, "pizza restaurant"
  - test in your browser (ex: http://localhost:3000)
  - if you don't have it, fork + clone + npm install + nodemon app.js

- Iteration 2: connect to the Live Session

  <!-- @LT: share link with Live session -->

- Iteration 3: 
  - copy the file `/bin/seeds.js` in your own project
  - read & try to understand the code

  <!-- 
    @LT: 
    - remember to share/save seeds file 
    - some students can not get it from live session (share on Slack or commit)
    - NOTE: sending the file on slack seems to give problems (try sharing as code snippet)
  -->

Time: 15min.




- Together:
  - explain concept of seeds file
  - why we call it "bin"
  - understand the code
  - update DB name.
  - run seeds file
  - note1: if your model is different or, if you have `unique`, it may not create your pizzas.
  - note2: `Pizza.deleteMany({})`




## Step Zero

- In the app from yesterday, we can replace the static objects with a query to the DB (allows to refresh + it will make code easier to follow when we do route params)

- INSTEAD OF:

  ```js
      const data = {
          title: "Pizza Margherita",
          price: 8,
          imgFile: "pizza-margherita.jpg",
          ingredients: ["mozzarella", "tomato sauce", "basilicum"]
      }

      res.render("pizza-page", data);
  ```

- DO:
  ```js
    Pizza.findOne({title: ""});
  ```
  
  <!-- @Luis: remember to connect to the DB (otherwise you get timeout) -->

- Example: https://github.com/Ironmaidens-Ironhack-Jan-2022/IronmaidensCommerce/commit/b65a5d226c363c5e15acde6c69b6b5ca03d2a443




## Practice: routes, mongoose and res.render

- modify the other pizza routes:
    - GET "/pizzas/veggie"
    - GET "/pizzas/seafood"
- instead of creating an object, now we want to get the info from the DB

- Bonus: 
  - display if pizza is Veggie or not (note: you may need to modify seeds file).
  - add other info like name of the Chef (may need to modify Model AND seeds file)
  - add a route for "Hawaiian Pizza"

Time: 12min.



## Spotify Account


- (break / lunch break): Spotify account
  - if you have a Spotify account, make sure you can login
  - if you don't, pls create one (it doesn't need to be premium)



- Cheatsheet (GET, POST):
  - https://gist.github.com/luisjunco/68bb7f09b8e95f225c67aece04522cf1