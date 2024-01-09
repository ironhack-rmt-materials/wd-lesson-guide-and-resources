

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
