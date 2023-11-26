

# Creating a Backend API


<!-- 

Status: ready


@LT: do this with the example we have in the students portal (projects + tasks )

-->



## REST APIs

- APIs

- REST APIs

- Slides: 
  <!-- @LT: skip for now (we will see REST in detail in m3) -->
  - https://docs.google.com/presentation/d/194i1dCV2vpqTN5T3yC5lysvfS-_fnEkok97QpaOtb3w/edit?usp=sharing

- Video: What is a REST API? (explains RESTful) (6 min., Mosh)
  - https://www.youtube.com/watch?v=SLwpqD8n3d0



## JSON Server

- It's an npm package.
- Allows you to create a mock REST API from a JSON file
- Ideal for prototype and mock APIs (ex. you're working on the frontend & need to wait for the backend to be ready).



## JSON Server Setup - Quick Start

Follow steps in the students portal.




## (skip) JSON Server Setup - Step by Step guide

Skip 

(it's equivalent to the one in "quick start")




## JSON Data and Endpoints

- JSON Server uses a specific JSON file structure to create REST API endpoints.

- Each key in your db.json file becomes an API endpoint


## Requesting All Records

- GET /projects
- GET /tasks


## Requesting a Single Record by id

- GET /projects/1
- GET /projects/2


## Invalid Requests

- JSON server will return an empty object


## Relationships

- Special key: same name as the related endpoint followed by Id
- Example: `projectId`




## Embedding Related Records

- `?_embed=tasks`
- Example: GET http://localhost:5005/projects/1?_embed=tasks




## Test with Postman


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

CRUD:

- Create: `POST /projects`

  ```json
  {
    "title": "Create a mock API using json-server",
    "description": "Create an API that we'll consume from  our React App"
  }
  ```

- Read (all): `GET /projects`

- Read (single project): `GET /projects/:id`

- Update: `PUT /projects/:id`

- Delete: `DELETE /projects/:id`


Test second resource: "tasks"
- `POST /tasks`
- `GET /tasks`



<!-- IMPORTANT -->
<!-- IMPORTANT -->

IMPORTANT: explain that json-server does not do any validation (you can put any data)

<!-- IMPORTANT -->
<!-- IMPORTANT -->



## Deployment

- Create repo + upload to GitHub
- Deploy on Adaptable.io



## (extra) Test in production

- Test with Postman



## (extra) Connect our React app

- Connect our React app to the API in production
  (for now, don't use env variables, just connect directly to production)

