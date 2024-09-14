
# React - State hook and events

<!--

Status: draft

@todo: 
- improve the planning for this unit (examples & steps to follow)
- create slides (ex. syntax, functional updates etc.)

-->


## Intro

- 2 Types of components
  - Function components
  - Class components


- Hooks:
  > Hooks let you use different React features from your components. 
  

- We've learned how to pass info with props
  - props = info that comes from outside of the component

- State:
  - Allows components to store internal data ("information")
  - We can use that information in JSX, when we describe the User Interface

> "State is similar to props, but it is private and fully controlled by the component."


- State: 
  - Store information that belongs to a component
  - Can change over time
  - We want to reflect the changes in the UI (JSX)





## State in function components


Option 1: 
- work on the app we built yesterday

Option 2 (preferred, since its easier to share the code): 
- work here: https://stackblitz.com/edit/react-s2s6wx?file=src%2FApp.js

  <!-- remember to FORK -->
  <!-- remember to FORK -->
  <!-- remember to FORK -->



DEMO: add a counter in `<Header />`:

  <!-- @LT: DEMO (we will do an exercise in a few moments)  -->

  - Display a message: "Number of likes: XXXX"
  - Add button 
  - Add onClick event
  - Explain these two patterns (before implementing the function):
    - `onClick={() => { console.log("clicked...")}}`
    - `onClick={increaseCounter}`
  - Explain how to send an argument:
    - `onClick={ () => {increaseCounter(20)}}`
  - Try to solve with a normal variable & see how that doesn't work.

      ```js
          let counter = 0;

          const increaseCounter = () => {
              console.log("increasing counter....")
              counter++;
              console.log(counter)
          }
      ```

  - Intro State: 
    - Store information that belongs to a component
    - Can change over time
    - We want to reflect the changes in the UI (JSX)




  - useState hook:
    - https://react.dev/reference/react/useState#reference

  -  Syntax:
    - `const [something, setSomething] = useState(initialValue);`


  - Solve with State

    ```js
      const [counter, setCounter] = useState(0);
    ```

    ```js
    counter++; // never
    setCounter( counter + 1 );
    setCounter( counter++ ); // avoid (will modify state directly)

    ```



## Practice: React State

<!-- @LT: remember to FORK  -->

Initial code:
https://stackblitz.com/edit/stackblitz-starters-723xsm?file=src%2FApp.js

Note: work on the App component (do not create other components)

Iteration 1:
- implement functionality to increase counter

Iteration 2:
- add a second button to decrease counter

Iteration 3:
- counter should never be below 0


Bonus 1: 
- if counter above 10, change bg color of the component
- Hint: you can use css classes (className). For example, displaying the following, depending on state:
    - `<div className="">`
    - `<div className="popular">` (if counter above 10)


Bonus 2:
- You may have solved the previous challenges using two functions (ex. "increaseCounter" and "decreaseCounter")
- Can we solve it with only one function ?

```jsx

const updateCounter = (diff) => {
  //.....
}


<button onClick={ () => updateCounter(+1)}>Like</button>
<button onClick={ () => updateCounter(-1)}>Dislike</button>

```

Bonus 3:
- Add 2 buttons so that the user can switch theme.
  - e.g., if user clicks "Switch to dark theme", display a dark background
  - e.g., if user clicks "Switch to light theme", display a light background

Bonus 4:
- Implement the functionality to change theme with a single button (ex. toggleTheme) and a single function.
- If theme changes, update the button (ex. display a different emoji).



Time: 20min. (try to do at least iterations 1, 2 and 3)

Solution 1 (with 2 functions):
- https://stackblitz.com/edit/stackblitz-starters-2abw6z?file=src%2FApp.js

Solution 2 (with only one function):
- https://stackblitz.com/edit/stackblitz-starters-xgf1gt?file=src%2FApp.js

Solution 3 (with `counter` + `theme`): 
- https://stackblitz.com/edit/react-hjbhv8?file=src/App.js

Solution 4 (with `counter` + single button to toggle `theme`): 
- https://stackblitz.com/edit/react-9uzbxh?file=src%2FApp.js


<!-- How: individual / in pairs -->



## Multiple state variables

In a component we can have multiple stateful variables

```js
const [counter, setCounter] = useState(0);
const [pizza, setPizza] = useState("margherita");
```



## (extra) add a counter to a component that repeats multiple times (ex. User/Movie)

See how the counter of each component is independent (state belongs to the component)

<!-- @todo: create example on stackblitz & share with students -->





## (skip) Explain: Functional update

Why should I use a function if the new state depends on the previous? Example: https://stackoverflow.com/a/57828519/11298742





## Using State correctly

<!-- @todo: create slides -->

- Remember (https://reactjs.org/docs/state-and-lifecycle.html#using-state-correctly):
  - Do Not Modify State Directly
    - note: `counter++` modifies state directly
  - State Updates May Be Asynchronous

- A Component will Re-render if:
  - receives new props from the outside
  - its own state changes

- Useful:
  - See how component re-renders when we update state
  - See state in React Dev Tools





## When should we use the state

- State: 
  - Store information that belongs to a component
  - Can change over time
  - We want to reflect the changes in the UI (JSX)



## State vs. Props

- See students portal


