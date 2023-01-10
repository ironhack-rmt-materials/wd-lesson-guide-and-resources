

# Postman and Axios

<!-- status: draft -->


## Intro


- APIs


- Introduce "characters API" 
  - https://ih-crud-api.herokuapp.com/characters
  - See documentation "AXIOS | POST, PUT and DELETE request"
  - explain the concept of `endpoint`
  - mention the concept of: `REST API`
  - test `GET` on the browser
  - how can we test other endpoints ? (ex. form with POST)


## Postman

Install Postman
  - https://www.postman.com/downloads/
  - Don't need to create an account (link at the bottom: "Skip")

- Test Characters API with Postman


## (optional) Introduce REST

- Slides: https://docs.google.com/presentation/d/194i1dCV2vpqTN5T3yC5lysvfS-_fnEkok97QpaOtb3w/edit?usp=sharing

- IMPORTANT: very brief (we will go in detail in module 3).


## (brief) Some options to send http requests

- Tools:
  - Postman
  - cURL
  - ...
- JavaScript code:
  - http request (https://stackoverflow.com/a/4033310/11298742)
  - fetch()
  - libraries (ex. axios)



## Axios

- Explain axios

  - It's a JavaScript library that we can use to make http requests
  - "Promise based HTTP client for the browser and node.js"
  - Can run in Browsers + Node.js
  - Supports promises
  - (Automatically transforms JSON into JS objects)
  - Installation
    - Using CDN
    - Using NPM: `npm install axios`
  - Using axios
    - Sample syntax

- Demo (with IronBnb API):
  - See documentation ("React | Connecting React app to the backend")
    - also here: https://github.com/luisjunco/exercise-react-ironbnb-client
  - Go to Stackblitz + install `axios`
    - Note: stackblitz seems to fail with latest version of axios.
    - Can fork this one (v.0.27.2): https://stackblitz.com/edit/js-hkgykx?file=index.js
  - get, post
  - final result: https://stackblitz.com/edit/js-hkgykx?file=index.js 



Practice:
- Write code to test all endpoints of Characters API using axios:
  - GET /characters
  - GET /characters/:id
  - POST /characters
  - PUT /characters/:id
  - DELETE /characters/:id

- Notes: 
  - keep in mind that the requests are asynchronous & the responses may arrive at different times
  - every time the code is executed, you will be sending those http requests. 
  - Advice: after each iteration, comment the previous code (so that it doesn't keep sending http requests.
  - Try to modify only the characters you have created (so that the others don't get unexpected results)


- base URL: https://ih-crud-api.herokuapp.com

- ![Characters API Endpoints](./images/characters-api-endpoints.jpg)

- Time: 20min.

- Solution: https://stackblitz.com/edit/js-ifpugl?file=index.js
  



## Do we need Axios for project2 ?

- We will use Axios a lot in m3.
- Project2: can be a bonus
  - ex. connect to a 3rd party API to get Weather info.

  

