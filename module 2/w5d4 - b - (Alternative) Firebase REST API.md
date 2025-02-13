

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


<!-- 

(Extra)

Some interesting content creators on youtube:
- https://www.youtube.com/@WebDevSimplified/playlists
- https://www.youtube.com/@programmingwithmosh/playlists
- https://www.youtube.com/@ColorCode-io/playlists
- https://www.youtube.com/@Fireship/playlists


-->



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




## Firebase REST API

Cheatsheet Firebase REST API:
- https://gist.github.com/luisjunco/1e98cfa855703f811a227aed6c599a4f




## How to test our REST API

Quick demo with axios (e.g. on stackblitz)

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


- Read (all): `GET /projects.json`
  - IMPORTANT: notice that it returns an object, not an array (!)
  <!-- @LT: Explain / demo: in our React app, we want to convert this to an array -->
  - Note: if there's no resources, firebase will return null

- Read (single record by id): `GET /projects.json/:id`
  - Note: if we make an invalid request (e.g. `/projects/abc.json`), firebase will return null

- Partial Update: `PATCH /projects.json/:id`

- Delete: `DELETE /projects.json/:id`



Quick demo with a second resource: "tasks"
- `POST /tasks.json`
- `GET /tasks.json`

<!-- @LT skip relationships -->


Explain that we don't have validation (you can put any data)




## Demo: connect our React app

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




## (skip) Relationships

Firebase Realtime Database is a NoSQL database.

It doesn't support traditional relationships (like foreign keys), but you can literally put anything any valid JSON in the DB, so it can be used to store relationships. The difference is that you'd need to manage relationships manually.


### Relationships Option 1: embedded documents (aka `denormalized`)

Example:

  ```json
  {
    "projectId-1": {
      "title": "Project 1",
      "description": "abc",
      "tasks": [
        {
          "title": "Initial Setup",
          "difficulty": 2
        },
        {
          "title": "Configure Routing",
          "difficulty": 3
        }
      ]
    }
  }
  ```


### Relationships Option 2: referencing data (aka `normalized`)


For example, you can have this collection of projects:

  ```json
    {
      "projectId-1": {
        "title": "Project 1",
        "description": "abc",
        "tasks": ["taskId-1", "taskId-2"]
      },
      "projectId-2": {
        "title": "Project 2",
        "description": "abc",
        "tasks": []
      }
    }
  ```

And this collection of tasks:

  ```json
  {
    "taskId-1": { "title": "Initial Setup", "difficulty": 2 },
    "taskId-2": { "title": "Configure Routing", "difficulty": 3 }
  }
  ```

In this case, you'd need to send 2 requests to the api.




## Warning on rules

- Explain that if we provide public access, anyone can CRUD any resource.
- It is possible to create more restrictive rules (and we should). In m3 we will also learn better patterns. 




## Pricing

- see: https://firebase.google.com/pricing 




## (skip) Firebase Auth

- Create a gist or leave it for students to do some research.

<!-- 

React Firebase Hooks:
- https://github.com/csfrequency/react-firebase-hooks


example project using react-firebase-hooks:
- https://github.com/alastairandthomas/iron-legacy
- note: uses Firestore + SDK instead of the rest api


Video from WebDevSimplified (1h)
- https://www.youtube.com/watch?v=PKwu15ldZ7k&t=34s
- uses: context API, private routes, etc
- note: this video is from 2020, some versions are outdated

-->


