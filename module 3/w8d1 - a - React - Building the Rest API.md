

# React - Building the Rest API



<!-- 

- Slides (REST + endpoints we will implement): 
  https://docs.google.com/presentation/d/194i1dCV2vpqTN5T3yC5lysvfS-_fnEkok97QpaOtb3w/edit?usp=sharing


- Students portal: some things highlighted


- Final result:
  https://github.com/Ironborn-Ironhack-March-2022/ironborn-project-management-server/commits/main


  note: the last commits are for Auth ("functionality to register" + "functionality for authentication")


- Approach: 
  - option 1: codealong (takes quite a bit of time, 4-6h )
  - option 2: giving students the code & ask them to try to understand it ? (they may feel overwhelmed)

-->

## Setup

- Create directory `project-management-fullstack`

- Ironlauncher: `npx ironlauncher project-management-server --json`
  - Auth? choose no.



## Part 1: intro to REST & best practices 


REST API Design Best Practices (see students portal):
- Use lowercase letters when naming endpoints
- Do not use underscores ( _ ), use hyphens (-)
- Use nouns instead of verbs in endpoint paths
- Use HTTP verbs to indicate the action (GET, POST, PUT, DELETE)
- Handle errors uniformly and respond with standard HTTP status codes


## Part 2: codealong


- Explain Express `res.json()`
  res.send()
  res.render()
  res.redirect()
  res.json()


- Explain ironlauncher commands:

`npx ironlauncher projectA --auth`
  the CLI will ask if you want to create "views"
  creates views directory & uses res.render()
`npx ironlauncher projectB --json`
  no views & res.json()
  (note: doesn't generate middleware directory, asumes not needed)
`npx ironlauncher projectC --auth --json`
  functionality for auth, middleware and no views (res.json())
  Project 3: use this option


- Main difference in the Backend from module 2:
  - we send json (we don't need to create views)
  - we will test with Postman
  - also, we will be running our express app in a different port (eg.5005)


- Explain goals & endpoints
  (see table with endpoints in the students portal)


- Plan together
  - models
  - routes


- Models:
  - Refresh embeded vs. Reference



- Build (advanced students can do that in pairs in breakout rooms)



Routes:
  - POST /projects
  - POST /tasks
  - GET /projects
  - GET /projects:projectId
  - PUT /projects:projectId
  - DELETE /projects/:projectId
  
Bonus:
- implement full CRUD for tasks


  
  - Minor improvement: when a project is deleted, remove also the associated tasks.
    - note: make sure to import Task model

  ```javascript
  Project.findByIdAndRemove(projectId)
    .then( deteletedProject => {
      return Task.deleteMany( { _id: { $in: deteletedProject.tasks } } );
    })
    .then(() => res.json({ message: `Project with id ${projectId} & all associated tasks were removed successfully.` }))
    .catch(error => res.status(500).json(error));
  ```  



- Enable CORS requests (see below)



# CORS

- Slides: 
  https://docs.google.com/presentation/d/1ccck25g9VXNxWA-GaXquyczZD2VnfD9Zx9lKKgFD2dk/edit?usp=sharing

  <!-- @todo: improve slides -->



## EXTRA CHALLENGES

Some options for extra challenges (they're not exclusive, can be combined):

- Bonus1: full CRUD on tasks
  - plan endpoints for tasks, following REST
  - implement the routes for those endpoints

- Bonus2: plan a React app to interact with this API
  - how would you build it (component structure etc)?

- Bonus3: build a React app to interact with this API
  - it is the next lesson in the students portal but some advanced students may want to start building it.
  - main thing to keep in mind is that you will need to enable CORS requests on the API
we will explain what is CORS and all those details a bit later but the code to do that is in "React | Building the Rest API" > "Enable CORS requests"

- Bonus3: deploy your API on heroku + mongoAtlas
  - Next week  we will do deployment for project3 but, if you want, you can also put this project online. 
  - You woud be able to test it with Postman/Compass, just as we're doing on localhost.





