

# React - Hooks & Lifecycle

<!-- 


Status: draft


@todo: 
- simplify theory (too many concepts for students)
- improve planning & examples
- Prepare exercise for them to practice
- CREATE SLIDES 
- CREATE SLIDES
- CREATE SLIDES
- CREATE SLIDES
- CREATE SLIDES
  - diagram mounting + updating & side effect (ex. https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/)
  - useEffect cheatsheet 


-->


## Show what we are going to build today

- Demo: https://react-characters-app.netlify.app/
- 2 main concepts:
  - API requests
  - Routing


<!-- @Luis: keep all code in App.js (it will make things easier for Routing) -->

## Pre-setup

`npx --yes create-react-app react-characters-app`





## Basic refresh Axios


- Intro/Refresh Characters API:
  - Base URL: https://ih-crud-api.herokuapp.com
  - list of characters: GET `/characters` (show on browser)
  - Show table with endpoints: w5d4 "AXIOS | POST, PUT and DELETE request"

- Refresh Axios
  - Open Stackblitz + GET list of characters
  - TASK:
    - Create a new character: POST /characters + send an object with `{name: "", occupation: "", weapon: ""}`
    - (Bonus) get the details of a specific character, update, delete...
    - Time: 10min.
  - SOLUTION: https://stackblitz.com/edit/js-hkgykx?file=index.js
  <!-- @Luis: ask users to disable auto-save in stackblitz (so that we don't repeat names many time) -->


- Remember, there's many ways to send http requests:
  - fetch(), libraries (ex. axios)


- Today, we will learn how to make HTTP requests in React & display the info





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


- Show diagram: 
  - https://wavez.github.io/react-hooks-lifecycle/
  - https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/


- Change in `props` or `state` = update


- "Render phase"
  > Pure and has no side effects.

- Explain concept of a side effect (read / modify)
  > A side effect is when a function relies on, or modifies, something outside its parameters to do something.

- (extra) explain "pure functions"
- React docs: https://reactjs.org/docs/components-and-props.html#props-are-read-only
  > Such functions are called “pure” because they do not attempt to change their inputs, and always return the same result for the same inputs.


  // SIDE-EFFECT:
  // - When we rely on or modify information outside

  // PURE FUNCTION:
  // 1. No side-effects
  // 2. Same input produces the same output



- How can we then make a call to an API ?

- Show wrong example (axios.get at the beginning of function component)

- Intro / Mention "hooks"
  - useXXXX
  - custom hooks

- Introduce useEffect()

  > useEffect Hook allows you to run side effects during all three lifecycle phases.

  ```js

    useEffect(didUpdate, dependencyArray);

    //run after a component has been mounted + after every component update
    useEffect(() => {
    });

    //run after a component has been mounted (only once)
    useEffect(() => {
    }, []);

    //run after a component has been mounted + every time "somePropsOrState" changes
    useEffect(() => {
    }, [somePropsOrState]);

  ```

  - See this cheatsheet: https://pbs.twimg.com/media/FEzs8twXsAYETEt?format=jpg&name=4096x4096
    ![this is the difference](./images/useEffect-summary.jpg)


## useEffect - Mounting phase

- run code in the mounting phase, only once.

`useEffect(() => {}, [])`

- The empty array [] means that “this effect doesn’t depend on anything”, 


## useEffect - Unmounting phase

- the function passed to useEffect may return a cleanup function.

```javascript
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

```javascript
 useEffect(() => {
   // ...
  }, [counter] ); 
```



## useEffect - Without dependency array

- Setting useEffect without the second argument [] (dependency array) will cause the useEffect to run on every render. 
- This could potentially cause an infinite re-rendering loop.





## Rules of hooks

Docs: https://reactjs.org/docs/hooks-rules.html


1. Only call hooks at the top level

  - DON'T call hooks inside loops, conditions, or nested functions !!
    - WHY: React relies on the order in which Hooks are called.

  - DO: always use hooks at the top level of your React function


  - Note: If we want to run an effect conditionally, we can put that condition inside our Hook.

    ```javascript
      useEffect( () => {
        if(condition){

        }
      }, []);
    ```

2. Only Call hooks from React functions

  - DON'T call hooks from regular JavaScript functions. !!

  - WE CAN: call hooks from React function components.
  - WE CAN: call hooks from custom hooks.



## Fetching data with useEffect

<!-- @todo -->


TASK:
- Implement functionality to display list of characters
  - For each character `<div className="character">Name: xxxx</div>`
- Display more info about the character (name, weapon)
- Bonus:
  - display only first 10 characters
  - css
  - button to delete one character

Time: 20-30m.




Steps:
- send query to API (useEffect)
- once we get the response, store update state


Mention:
- initialize to empty array vs. null etc
  - ex: `const [charactersArr, setCharactersArr] = useState([]);`
  - Common problem: we initialize to undefined + we iterate with .map()
- conditional rendering (display a message while loading)
  - ex: `charactersArr.length === 0 ? <p>loading...</p> : renderList()`




## IMPORTANT CONCEPTS

- If `props` or `state` change, React will (can) re-render the component.

- Avoid side effects during render phase

- COMMON MISTAKE: invoke function in JSX & that function has side-effect (eg. fetch data)

- EXPLAIN HOW TO MAKE API REQUEST & how to render results in jsx 


## Exercise

API call to characters API
- Task: display list of characters () 
  <!-- @todo: this contains the solution -->
  https://stackblitz.com/edit/react-hhhsgc?file=src/App.js

- Possible solution (API call & conditional rendering):
  https://stackblitz.com/edit/react-hhhsgc?file=src/App.js



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


<!-- 
  @todo: 
  - make an easier diagram  
  - Mounting: execute (get JSX) + DOM manipulation

-->

React Hooks Lifecycle:
https://wavez.github.io/react-hooks-lifecycle/



## APIs

OMDB API: 
- http://www.omdbapi.com/
- To get an API key we just need to signup & recieve email: http://www.omdbapi.com/apikey.aspx
- Example Query: https://www.omdbapi.com/?i=tt0133093&apikey=b6ce61f6


Characters API:
- https://ih-crud-api.herokuapp.com/characters
