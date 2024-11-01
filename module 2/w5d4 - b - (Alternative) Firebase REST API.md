

# Firebase REST API



## Discover: what's a REST API?

Task 1: watch this video 
  - What is a REST API? (explains RESTful) (6 min., Mosh): https://www.youtube.com/watch?v=SLwpqD8n3d0

Task 2:
  - Define the endpoints for a REST API the allows to CRUD "recipes"
  - Example:
    - GET /recipes -- get a list of recipes
    - ...
    - ...

Time: 12min.


---


- (skip for now) Slides REST: 
  <!-- @LT: skip for now (we will see REST in detail in m3) -->
  - https://docs.google.com/presentation/d/194i1dCV2vpqTN5T3yC5lysvfS-_fnEkok97QpaOtb3w/edit?usp=sharing


- See API we used yesterday (follows REST): 
  - https://project-management-api-4641927fee65.herokuapp.com/projects



## Intro to this unit

- project 2 requirements: 
  - CRUD on an API

- Options:
  - Option 1: research & use an existing external API
    - example: https://github.com/public-apis/public-apis
  - Option 2: create your own API with Firebase

- Topics we will see in this unit:
  - How to get a REST API from Firebase
  - How to test it

- Firebase intro
  - Service from Google Cloud
  - Cloud-Based Backend: Firebase provides a comprehensive backend solution with tools like real-time databases, cloud storage and authentication. Allows developers to build applications without managing their own servers.
  - Exposes a REST API





## Creating an account at Firebase

Note: setup is very straight forward & at the moment it doesn't require payment details.


## Configure your project

- Click "Create a project"
- Choose a name for your project
- Google Analytics: can disable it (we will not use it)
- (takes 1-2 minutes)

- Build > "Realtime Database"
  - IMPORTANT: we will use "Realtime Database", not "Firestore Database"
  <!-- IMPORTANT -->
- Click: Create Database
- Select location (e.g. Europe)
- Select "Security rules"
  - Choose start in "locked mode"

- Update the rules to give public access to all users:
    ```json
    {
      "rules": {
        ".read": true,
        ".write": true
      }
    }
    ```
  - Click "Publish"


- Firebase will automatically expose a REST API.
  - The api url looks like “baseURL/resource.json”
  - Example endpoints:
    - "GET /recipes.json"
    - "GET /recipes/:recipeId.json"
    - "POST /recipes.json"
    - "PATCH /recipes/:recipeId.json" (there’s also PUT)
    - "DELETE /recipes/:recipeId.json"


- Quick demo with axios (e.g. on stackblitz)



## Intro to Postman


- (brief) Some options to send http requests:
  - Tools:
    - Postman
    - cURL
    - ...
  - JavaScript code:
    - http request (https://stackoverflow.com/a/4033310/11298742)
    - fetch()
    - libraries (ex. axios)



Install Postman
  - https://www.postman.com/downloads/
  - Don't need to create an account (link at the bottom: "Skip")


How to send a request:
- Example: GET https://dog.ceo/api/breeds/image/random





## Test REST API endpoints


- Create: `POST /projects.json`:

  ```json
  {
    "title": "Configure a REST API using Firebase",
    "description": "Create an API that we'll consume from  our React App"
  }
  ```

  <!-- @LT: share URL and ask students to create a project  -->


- Read (all): `GET /projects.json`:
  - IMPORTANT: notice that it returns an object, not an array (!)
  <!-- @LT: Explain / demo: in our React app, we want to convert this to an array -->
  - Note: if there's no resources, firebase will return null

- Read (single record by id): `GET /projects.json/:id`:
  - Note: if we make an invalid request (e.g. `/projects/abc.json`), firebase will return null

- Partial Update: `PATCH /projects.json/:id`:

- Delete: `DELETE /projects.json/:id`:




Test second resource: "tasks"
- `POST /tasks.json`
- `GET /tasks.json`



Explain that we don't have validation (you can put any data)



<!--
test: Relationships
- Example: `projectId`

test: Embedding Related Records
- Example: GET http://localhost:5005/projects/1?_embed=tasks
-->



## (extra) Connect our React app

- Connect our React app to the API in production
  (for now, don't use env variables, just connect directly to production)


- Converting the object we get from Firebase to an array:

  ```jsx
  const projectsObject = response.data;

  const projectsArr = Object.keys(projectsObject).map((id) => ({
      id,
      ...projectsObject[id],
  }));

  setProjects(projectsArr);
  ```


## Pain points

- created: Firebase returns a 200 instead of 201.
- list of items (e.g. projects.json): Firebase returns an object, not an array
- wrong request: on the browser, you may get a CORS error


## Pricing

- see: https://firebase.google.com/pricing 

