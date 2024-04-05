

# w7d4



## Day planning

- LAB Q&A [20m]

- Refresh main contents we've seen so far ? [40m]
  - routes
  - req.params, req.query, req.body
  - mongoose
    - schema, model
    - mongoose methods

    <!-- alternative: provide a 30m. recording -->


- Refresh: relationships + populate [40m]
  - opt1: refresh with some notes
  - opt2: implement on the app from yesterday ? 


- Ironlauncher [1h]
  - create "project-management-server"
  <!-- alternative: skip ironlauncher for now ? (and start extracting routes to specific file) -->

- REST API
  - REST
    - what is REST
    - REST API Design - Best Practices
  - API Documentation (see endpoints)
  - git init
  - Models
  - Routes:
    - create files & mount in app.js:
      - project.routes.js
      - task.routes.js
    - POST /api/projects
      - req.body
      - Project.create()
      - test with postman
    - POST /api/tasks
      - test with postman
    - GET /api/projects
    - Remaining Routes - Projects:
      - GET /api/projects/:projectId (with populate)
      - PUT  /api/projects/:projectId
      - DELETE  /api/projects/:projectId
      - test with postman
    - CORS 

  <!--
  - Explain relationships with examples [2h]
    - short breaks often
  -->




## Active Learning / Afternoon

- Submit project preferences
  - Deadline: tomorrow 9am.

- Mini Project - REST API - Day 4 (in groups)

- Watch Recording "Auth: intro and hash algorithms" (1h): https://www.loom.com/share/99e0abae2c9346a3ba84d1e178c06b48?sid=e471b840-b8a6-44a1-9070-4f5a5f662518



