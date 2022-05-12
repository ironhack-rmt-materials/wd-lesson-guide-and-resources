

# React - Hooks & Lifecycle

<!-- 


Status: draft


@todo: 
- simplify theory (too many concepts for students)
- improve planning & examples

-->



## Pre-setup

`npx create-react-app react-characters-app`



## Basic refresh Axios

- Open Stackblitz and make a simple request to this API:
  - https://ih-crud-api.herokuapp.com/character

- Today, we will learn how to make HTTP requests in React & display the info

- Remember, there's many ways to send http requests:
  - fetch(), libraries (ex. axios)





## Component Lifecycle

<!-- students portal (highlighted)  -->


(Intro) Show how components are executed:
  - add console.log() for each component on the app we created yesterday ("popcorn time")
  - See how each function component is executed
  - See that, when `state` or `props` change, a component is re-rendered


Stages:
- Mounting
- Updating
- Un-mounting


- Show diagram: https://wavez.github.io/react-hooks-lifecycle/

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

  `useEffect(didUpdate, dependencyArray)`


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

1. Only call hooks at the top level

  - DON'T call hooks inside loops, conditions, or nested functions !!
    - WHY: React relies on the order in which Hooks are called.

  - DO: always use hooks at the top level of your React function

If we want to run an effect conditionally, we can put that condition inside our Hook.

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


## Diagrams

React Lifecycle methods diagram (class components):
https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/


React Hooks Lifecycle:
https://wavez.github.io/react-hooks-lifecycle/



## APIs

OMDB API: 
- http://www.omdbapi.com/
- To get an API key we just need to signup & recieve email: http://www.omdbapi.com/apikey.aspx
- Example Query: https://www.omdbapi.com/?i=tt0133093&apikey=b6ce61f6


Characters API:
- https://ih-crud-api.herokuapp.com/characters
