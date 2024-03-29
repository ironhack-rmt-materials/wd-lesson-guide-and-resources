

# w7d2



## Day planning

- LAB Q&A [20m]

- Refresh [20m]
  - express routes
    - ex. `app.get(path, callbackFn)`
    - req, res, next
  - different ways to send a response
    - `res.send()`
    - `res.sendFile()`
    - `res.json()`
  - Middleware
    - diagram: https://education-team-2020.s3.eu-west-1.amazonaws.com/web-dev/m2/expressjs/express-middleware-1.png
    - show example of a custom middleware function
    - (extra) see documentation for app.get
      - `app.get(path, callback [, callback ...])`
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

- (extra) introduce req.params [30m]
  <!-- why: w7d3 has a lot of contents, can be good to introduce it today -->


- MongoDB Intro + MongoDB Compass + CRUD Operations + Exercise [2.5h]

- Data Models ? [20m]

  <!-- 
  
  consider doing a quick intro to "Data Models" + relationships.
  (so that we're more familiar with that concept when we do relationships)
  
  -->


## Active Learning

- 2pm: LAB | MongoDB - Advanced Querying (individual)
- 3:30pm Mini Project - REST API - Day 2 (in groups)