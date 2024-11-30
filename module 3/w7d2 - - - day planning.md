

# w7d2

<!--
notes:
- include "req.params" + "req.query" today (w7d2 workload is not very high)
-->


## Day planning

- LAB Q&A [20m]

- Explain: CORS [20m]
  - slides: https://docs.google.com/presentation/d/1ccck25g9VXNxWA-GaXquyczZD2VnfD9Zx9lKKgFD2dk/edit?usp=sharing

  <!-- @todo: improve slides cors -->


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





- (extra) introduce URL params (req.params) [30m]
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




- (extra) introduce query string (req.query) [40m]
  <!-- 
  @todo: 
  - can also be a self-guided video (haven't found any good quality video, so can record it) + exercise
  - note: it can also be as part of the afternoon activities (since today's workload is not that high)
  -->


 - Practice: query string

  - Initial code: https://stackblitz.com/edit/stackblitz-starters-ruevx3?file=index.js

  - Your task: using query string, implement functionality to filter by number of tracks:
    - GET /albums?min_number_of_tracks=10

  - Bonus: implement functionality to filter by number of tracks and genre:
    - GET /albums?min_number_of_tracks=10&genre=rock

  - Time: 15min.

  
  Solution: https://stackblitz.com/edit/stackblitz-starters-wcpstt?file=index.js
  





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

- Bonus: 
  - Follow the steps in the unit from tomorrow "Mongoose | Introduction"
  - Codewars Katas

<!-- 
Bonus Exercise: 
- Practice req.query

-->