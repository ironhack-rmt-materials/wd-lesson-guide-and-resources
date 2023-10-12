
# w7d5



<!--

@Luis: 
- tell TAs that there's NO LAB KICK-OFF today.
- ask p3 preferences (ex. ask in the afternoon, with DL monday 9am)

Friday: try to finish earlier.

-->


## Warmup:

- Questions from yesterday's lab
  
- Refresh
  - lifecycle & hooks
  - side-effect & useEffect
  - Routing


## Move API URL to .env

Store API baseUrl in .env (since we're using Vite, make sure your environment variable starts with the prefix VITE_)
  - ex. `process.env.VITE_API_URL`


1. Create your environment variables in .env file
  - make sure variables start with `VITE_`
  - ex. "VITE_API_URL"

2. To use them: `import.meta.env.xxx`
  - ex. "import.meta.env.VITE_API_URL"


Note: `.env` is not in .gitignore
(but `*.local` will be ignored; for example: ".env.local")







## (Extra) Conditional rendering while resources are loading




## Add button to delete character from the API
- Concepts that will appear:
  - Send request to the API without useEffect (ex. when user clicks on a button)
  - redirect with `useNavigate`: https://reactrouter.com/en/main/hooks/use-navigate
  - Fix: list of characters not updated in App.js
    - (depending on how we implemented code) we may still have the old list of characters
    - to fix that:
      - in App.js: create a reusable function `getCharactersFromApi()`
      - in child component: 
  We may need to send a new request to the API (to get the new list of characters)



Script to create multiple characters:
https://stackblitz.com/edit/js-pn6cnh?file=index.js


## (Discuss) 2 API requests vs. 1 API request in App + pass info as props.
<!-- @Luis: skip (just discuss) -->
- In the App from yesterday: show how it is possible to send only a single request to the API (if the API send an array with the details for all resources, we can avoid making a request for each resource).
- Notes: 
  - takes a bit longer than it seems (30m + 15m)
  - when you access directly `/characters/1`, the app will fail, if we don't do conditional rendering (it is a good moment to see component lifecycle, adding some console.logs)
- Sample commit: https://github.com/RemoteRaccoons-Ironhack-Nov-22/raccoons-react-characters-app/commit/d5b72fe8454bc2292de353c7da3890f833acdca6
- Note: `const {characterId} = useParams();` give you a `String`


## (Extra) common pain points when sending requests to API

- Pain point 1: Iterate with .map() though something that is not an array:

  ```js
  const [charactersArr, setCharactersArr] = useState(); //initialized to undefined

  // ...

  return(
    <h2>List:</h2>
    {charactersArr.map()}
  );

  ```

- Pain point 2: trying to access properties of something that is not an object

  ```js
  const [details, setDetails] = useState(); //initialized to undefined

  // ...

  return(
    <h2>Details:</h2>
    {details.name}
  );

  ```

  - Options:
    - initialize array to empty array
    - optional chaining operator (https://www.joshwcomeau.com/operator-lookup?match=optional-chaining)
    - conditional rendering      


## (Extra) Refresh "REST APIs"

<!-- Or watch REST video -->



## Work on IronBnb (I have created a minilab for this)



## Afternoon:
  - show 2 examples of m3 projects.
    - first project with focus on MVP requirements (auth, 3 models, CRUD) + second project with other functionality
    - https://meet-them-all.netlify.app/
    - https://meetive.netlify.app

  
  - they can start thinking who they want to do it with + what they want to build


- Should I start project3 this weekend ?
  - advice: start thinking & planning
  - wait for coding





<!--

IMPORTANT
IMPORTANT
IMPORTANT

- if we ask any student to do project individual, tell them asap

IMPORTANT
IMPORTANT
IMPORTANT

-->



<!-- 

@LT:

Monday NEXT WEEK (week8):
- we build a REST API
- most of those concepts are something they already know (we did it in m2)
- new concepts:
  - REST
  - res.json()
  - how to test the API with Postman
  - CORS

- One possible approach could be asking students to follow this unit as self-guided (note: they also have a lab & assessment)
- If so, provide a video explaining the new concepts & how to test the API with Postman

-->


