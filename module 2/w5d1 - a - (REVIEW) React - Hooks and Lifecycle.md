

# React - Hooks & Lifecycle

<!-- 


Status: draft


@todo: 
- IMPROVE PLANNING & NOTES
- simplify theory (too many concepts for students)
- improve planning & examples
- Prepare exercise for them to practice
  - diagram mounting + updating & side effect (ex. https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/)
  - useEffect cheatsheet 



Notes:
-- explain how to make calls to an API (when component mounting & after component mounted with user interaction)
-- bonus: video of why we need to do it this way
-- also, improve the code for JSX & conditional rendering (some of the examples use patterns difficult for students)
   



-->




## Show what we are going to build today

- Demo: https://react-characters-app.netlify.app/
- 2 main concepts:
  - API requests
  - Routing


<!-- @Luis: keep all code in App.js (it will make things easier for Routing) -->





## Introduce "characters API"

- What's an API


- Example 1 (rick and morty, readonly):
  - https://rickandmortyapi.com/api/character/1

- Example 2 (characters api): 
  - https://ih-crud-api.herokuapp.com/characters
- See documentation: w5d4 "AXIOS | POST, PUT and DELETE request"
  - ![Characters API Endpoints](../media/images/characters-api-endoints.png)
- explain the concept of `endpoint`
- mention the concept of: `REST API`
- test `GET` on the browser
- how can we test other endpoints ? (ex. form with POST)

- (extra) Chrome extension to parse json: 
  - https://chromewebstore.google.com/detail/json-formatter/bcjindcccaagfpapjjmafapmmgkkhgoa


## Refresh Axios GET

Demo:
- Open Stackblitz + GET list of characters
  <!-- (note: on stackblitz, use axios v.0.27.2) -->
- Example: https://codesandbox.io/s/icy-rain-igs74w?file=/src/index.js


Diagram promises (fulfilled, rejected): 
- https://www.javascripttutorial.net/wp-content/uploads/2020/03/JavaScript-Promise-state.png



## Practice: Axios Post request

Initial code (it already has axios installed): https://stackblitz.com/edit/js-8lg6qc?file=index.js

Iteration 0:
  - Go to settings and choose "Page reload" + "Save" (so that we don't send a request every time we change the code)

Iteration 1: create a character with your name
- Using axios, create a new character in our API.
- BaseURL: https://ih-crud-api.herokuapp.com
- We need to send POST request to `/characters`
- In the body of the request, send an object with `{name: "", occupation: "", weapon: ""}`

Bonus 1: get the details of a specific character
Bonus 2: update your character
Bonus 3: delete your character

Time: 12min.



Endpoints:
![characters api](../media/images/characters-api-endoints.png)

Hints:
  - Example with a GET request https://codesandbox.io/s/icy-rain-igs74w?file=/src/index.js
  - Documentation for POST: https://axios-http.com/docs/post_example


Solution: 
  - https://codesandbox.io/s/lively-cache-olz44t?file=/src/index.js


  <!-- 

  @LT: 

  - On Stackblitz, can install `axios@0.27.2`

  - Ask students to DISABLE AUTO-SAVE (so that we don't repeat names many time)
    - on CodeSandbox: https://stackoverflow.com/a/74508939/11298742
  
  -->





- Remember, there's many ways to send http requests:
  - fetch(), libraries (ex. axios)




## (optional) introduce the syntax that we'll see today (useEffect)

Example API request in React:
https://stackblitz.com/edit/vitejs-vite-gn4dd9?file=src%2FApp.jsx

<!-- @todo: create components (Header, Footer, CharactersList) -->



## Intro/Explain: concept of Side-Effect

Alternative: 
- ask students to do some research
- "what is a side effect in programming?"

Explain concept of a SIDE-EFFECT:
  > A side effect is when a function relies on, or modifies, something outside its parameters to do something.
  - ie. when we read/modify information outside

Examples: https://stackblitz.com/edit/js-sefk58?file=index.js

  <!-- 
  
  @todo: 
  - add definition of "side-effect" to the slides
  - example 1: function reading variable from parent scope
  - example 2: function modifying variable in the parent scope
  
  -->


- (extra) explain "pure functions"

  - PURE FUNCTION:
    1. No side-effects
    2. Same input produces the same output



- Today, we will learn how to make HTTP requests in React & display the info




## (DEMO) sending API requests in our React App.

<!-- DEMO ONLY -->

How:
- Show demo on the app from yesterday (popcorn-time).

What we will do: 
- in the Header, display the number of characters in the API.

<!--
@Luis: 

- display number of characters
- DO NOT display list of characters (we will do an exercise later)

-->

Steps:
- npm i axios
- send request

  ```js

  import axios from "axios";

  //...

  const baseURL = "https://ih-crud-api.herokuapp.com";

  axios
    .get(baseURL + '/characters')
    .then((response) => {
      console.log(response.data);
    })
    .catch((e) => {
      console.log(e);
    });
  ```


Step 1: 
  - Store numberOfCharacters in a `NORMAL VARIABLE`
  - Issue: UI not updated

Step 2: 
- Store numberOfCharacters in `STATE`
- Issue: Re-render loop (intro useEffect & side effects).

Step 3: 
- quick demo with `useEffect()`



## Initial Setup

- navigate to module2 directory
- `npm create vite@latest react-characters-app -- --template react`
- cd react-characters-app
- code -r .
- npm install
- npm run dev

To run on a specific port:
- npm run dev -- --port=3002



## Component Lifecycle

<!-- students portal (highlighted)  -->


<!--
  Alternative:
  - start by showing a basic app (stackblitz) where we send an API request 
  - ex. to get the details of one character
  - see the code with students (useEffect etc) and then explain why we need to do it this way.

-->


(Intro) Show how components are executed:
  - add console.log() for each component on the app we created yesterday ("popcorn time")
  - See how each function component is executed
  - See that, when `state` or `props` change, a component is re-rendered


Stages:
- Mounting
- Updating
- Un-mounting



- Slides "Hooks and Lifecycle":
  - https://docs.google.com/presentation/d/1kAtC4-ONnFGdfLAGhAtNYSl09ViBSUUgyA4PpEbfDYg/edit?usp=sharing


- Show diagrams: 
  - Hooks: https://wavez.github.io/react-hooks-lifecycle/
  - Classes: https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/


React hooks (summary & list of basic hooks):
https://legacy.reactjs.org/docs/hooks-reference.html


- Change in `props` or `state` = update


- "Render phase"
  > Pure and has no side effects.


- React docs: https://reactjs.org/docs/components-and-props.html#props-are-read-only
  > Such functions are called “pure” because they do not attempt to change their inputs, and always return the same result for the same inputs.




- How can we then make a call to an API ?

- Show wrong example (axios.get at the beginning of function component)

- Introduce useEffect()

  > Sometimes, we want to run some additional code after React has updated the DOM.

  > useEffect Hook allows you to run side effects during all three lifecycle phases.


  ```js

    useEffect(didUpdate, dependencyArray);

    //run after a component has been mounted (only once)
    useEffect(() => {
    }, []);

    //run after a component has been mounted + every time "somePropsOrState" changes
    useEffect(() => {
    }, [somePropsOrState]);


    //run after a component has been mounted + after every component update
    useEffect(() => {
    });
    

  ```

  - See this cheatsheet: https://pbs.twimg.com/media/FEzs8twXsAYETEt?format=jpg&name=4096x4096
    - Image: ![useEffect summary](../media/images/useEffect-summary.jpg)




## useEffect - Mounting phase

- run code in the mounting phase, only once.

`useEffect(() => {}, [])`

- The empty array [] means that “this effect doesn’t depend on anything”, 



## (skip) useEffect - Unmounting phase

- the function passed to useEffect may return a cleanup function.

```js
  useEffect(() => {
    console.log("useEffect - Mounting (initial render)");
    const id = setInterval(() => {
      setCount((prevCount) => prevCount + 1);
    }, 1000);
 
    // Return a "cleanup function" which will run automatically
    // before the component is removed from the DOM
    return () => {
      console.log("Cleanup - Component Unmounting");
      clearInterval(id);
    };
  }, []);
```




## useEffect - Conditional updates

- dependency array.

```js
 useEffect(() => {
   // ...
  }, [counter] ); 
```



## useEffect - Without dependency array

- Setting useEffect without the second argument [] (dependency array) will cause the useEffect to run on every render. 
- This could potentially cause an infinite re-rendering loop.






## Practice: useEffect (get a list of characters)

<!-- 

Note: students need a lot of guidance to be able to do this task for the first time (unless we've done any similar example before)

-->


Initial code: https://stackblitz.com/edit/vitejs-vite-qpqbnd?file=src%2FApp.jsx


Iteration 1: display the number of characters (in App.jsx)
- In App.js: use `useEffect` & `axios` to get a list of characters from the API.
- Endpoint: GET "https://ih-crud-api.herokuapp.com/characters"
- Once you have the list of characters, display that in the console.
- Now, display the number of characters in the JSX (ex. so that the user can see how many characters there are).


Iteration 2: display a list of characters (in App.jsx)
- Display info about each character in the user interface.
- Ex. for each character, something like this:
  ```html
    <div className="character">
      Name: xxxx
      Weapon: xxxx
    </div>
  ```

- Notes:
  - We will work on `App.jsx` (for now, DO NOT CREATE OTHER COMPONENTS)
  - You will need a stateful variable to store the list of characters
    - Ex.: ` const [characters, setCharacters] = useState([]); `
  - Once we get the response from the API, update state so that React re-renders the component.
  - In our JSX, we need to iterate through the stateful variable. Ex.: `charactersArr.map()`

Bonus:
  - Display only first 10 characters
  - Add css
  - Implement a button to delete one character (when the user clicks, we send a request to the api)

<!-- @LT: share with them the example we did earlier -->

How: work in pairs.
Time: 30m.






## (Extra) common pain points when sending requests to API

  - Pain point 1: Iterate with .map() though something that is not an array:

    ```js
      const [charactersArr, setCharactersArr] = useState(); //initialized to undefined

      return(
        <h2>List:</h2>
        {charactersArr.map()}
      );

    ```

- Pain point 2: trying to access properties of something that is not an object

    ```js
      const [details, setDetails] = useState(); //initialized to undefined

      return(
        <h2>Details:</h2>
        {details.name}
      );

    ```

  - Options:
    - initialize array to empty array/object
    - optional chaining operator (https://www.joshwcomeau.com/operator-lookup?match=optional-chaining)
    - conditional rendering




## Example of when you need dependency array

- Navbar includes list of characters (when user clicks, we want to see the details of a new character)
- Component `CharacterDetails` always present (never unmounted)

  ```jsx
    <nav>
      <Link to="/characters/1">One</Link> | 
      <Link to="/characters/2">Two</Link> | 
      <Link to="/characters/3">Three</Link> | 
    </nav>


    <Routes>
      <Route path='/' element={<CharactersList />} />
      <Route path='/characters/:characterId' element={<CharacterDetails />} />
      <Route path='*' element={<h2>Page Not Found</h2>} />
    </Routes>
  ```




## Rules of hooks

Docs: https://reactjs.org/docs/hooks-rules.html


1. Only call hooks at the top level

  - DON'T call hooks inside loops, conditions, or nested functions !!
    - WHY: React relies on the order in which Hooks are called.

  - DO: always use hooks at the top level of your React function


  - Note: If we want to run an effect conditionally, we can put that condition inside our Hook.

    ```js
      useEffect( () => {
        if(condition){

        }
      }, []);
    ```

2. Only Call hooks from React functions

  - DON'T call hooks from regular JavaScript functions. !!

  - WE CAN: call hooks from React function components.
  - WE CAN: call hooks from custom hooks.




## IMPORTANT CONCEPTS

- If `props` or `state` change, React will (may) re-render the component.

- Avoid side effects during render phase

- COMMON MISTAKE: invoke function in JSX & that function has side-effect (eg. fetch data)

- EXPLAIN HOW TO MAKE API REQUEST & how to render results in jsx 




## Cheatsheet

- useEffect() cheatsheet:
  https://stackblitz.com/edit/react-ogf6xl?file=src/App.js


- useEffect() cheatsheet with API request:
  <!-- @todo -->


- React hooks cheatsheet: 
  https://react-hooks-cheatsheet.com/useeffect



## Diagrams

React Lifecycle methods diagram (class components):
https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/


React Hooks Lifecycle:
https://wavez.github.io/react-hooks-lifecycle/



## APIs

OMDB API: 
- http://www.omdbapi.com/
- To get an API key we just need to sign-up & receive email: http://www.omdbapi.com/apikey.aspx
- Example Query: https://www.omdbapi.com/?i=tt0133093&apikey=b6ce61f6


Characters API:
- https://ih-crud-api.herokuapp.com/characters


