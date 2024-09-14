

# w7d2



## Day planning

- LAB Q&A [20m]

- Explain: CORS [20m]


- Refresh [20m]
  - express routes
    - ex. `app.get(path, callbackFn)`
    - req, res, next
  - different ways to send a response
    - `res.send()`
    - `res.sendFile()`
    - `res.json()`
  - nodemon
    - in development, we will usually run with nodemon
  - (extra) explain "npm scripts"
    ```json
    {
      "scripts": {
        "start": "node app.js",
        "dev": "nodemon app.js"
      }
    }
    ```
  - Middleware
    - diagram: https://education-team-2020.s3.eu-west-1.amazonaws.com/web-dev/m2/expressjs/express-middleware-1.png
    - show example of a custom middleware function
    - (extra) see documentation for app.get
      - `app.get(path, callback [, callback ...])`




- (extra) introduce req.params [30m]
  <!-- why: w7d3 has a lot of contents, can be good to introduce it today -->
  <!-- Sample repo: https://github.com/ironhack-apr2024-theScriptSociety/iron-restaurant -->



 - Practice: URL params

  - Initial code: https://stackblitz.com/edit/stackblitz-starters-6lhrym?file=index.js
  - Your task: using url params, implement a generic route to get the details of one artist. Example:
    - GET /artists/1
    - GET /artists/2
    - GET /artists/3

  - Time: 15min.

  - Solution: https://stackblitz.com/edit/stackblitz-starters-gvhcqw?file=index.js
  
    <!-- @LT: show how they can test a route in stackblitz (ex. /artists) -->



- (extra) introduce req.query [40m]
  <!-- @todo: create exercise -->


- MongoDB Intro + MongoDB Compass + CRUD Operations + Exercise [2h]

- Data Models ? [20m]

  <!-- 
  
  consider doing a quick intro to "Data Models" + relationships.
  (so that we're more familiar with that concept when we do relationships)
  
  -->


## Active Learning

- (individual) LAB | MongoDB - Advanced Querying
  - Note: to import the db, you can use MongoDB Compass.
  
- (in groups) Mini Project - REST API - Day 2

- Bonus: follow the steps in the unit from tomorrow "Mongoose | Introduction"

