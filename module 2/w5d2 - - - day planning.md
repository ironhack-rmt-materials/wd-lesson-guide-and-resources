
# w5d2


<!-- 

m2-m3 swap:

- Codealong: follow students portal

- Why: with the new schedule, this is the time where we build a React app with full CRUD

-->



## Warmup:

- LAB Q&A
  
- Refresh
  - lifecycle & hooks
  - side-effect & useEffect
  - common pain points when sending requests to an API
    - ex. `useState()` + `undefined.map()`




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




<!-- IMPORTANT: if we ask any student to do project individual, tell them asap -->




