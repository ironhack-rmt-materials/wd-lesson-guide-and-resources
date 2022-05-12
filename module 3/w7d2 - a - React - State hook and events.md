
# React - State hook and events

<!--

Status: draft

@todo: 
- improve the planning for this unit
- update planing to hooks
- prepare examples
- note: it can also be good to prepare a boilerplate app to start speaking about state (see: "/Luis/pro/Ironhack/_playground/first-react-app/first-react-app")

-->


## Intro

- 2 Types of components
  - Function components
  - Class components

- We've learned how to pass info with props
  - props = info that comes from outside of the component

- State:
  - Allows components to store internal data ("information")
  - We can use that information in JSX, when we describe the User Interface

> "State is similar to props, but it is private and fully controlled by the component."


- Things to keep in mind:
  - ~~state is an object~~
  - state can change overtime
  - state "lives" in the component and belongs to the component itself (props come from outside)
  - changes in state can affect component rendering and what the component displays


- Function vs Class components
  - State available in class components
  - In function components with "hooks"



## State in function components

Example: we will add a counter
- Counter +1
- Bonus:
  - add a button to decrease counter
  - counter will never be below 0
  - if counter above 10, change bg color



## (extra) State in class components


<!-- 

- 2 ways to initialize (show syntax):
  - with constructor method
  - Alternative class syntax - without constructor method

- Note:
  - "Notice how state is defined as an object".
  - We can have as many key-value pairs as we need


- Demo

- Initial code: https://stackblitz.com/edit/react-dimt6c?file=src/App.js
  - list of recipes
- Goal: https://stackblitz.com/edit/react-fztnxt?file=src/App.js
  - in the header, add a button "like this app" and a counter with the amount of clicks


- IMPORTANT:
  - To manipulate the state, we have to use setState() method
  - never try to manipulate the state directly!

  ```
    this.state.count++; // BAAAAAD
  ```

- setState (see documentation):
  `setState(updater, [callback])`
  - First argument: Function or Object
  - Second argument (optional): callback


-->


- Remember (https://reactjs.org/docs/state-and-lifecycle.html#using-state-correctly):
  - Do Not Modify State Directly
    - note: `counter++` modifies state directly
  - State Updates May Be Asynchronous
  - State Updates are Merged (class components)
    - ("When you call setState(), React merges the object you provide into the current state.")

- Useful:
  - See how component re-renders when we update state
  - See state in React Dev Tools



## When should we use the state

- State: 
  - Store information that belongs to a component
  - Can change over time
  - We want to reflect the changes in the UI (JSX)



## State vs. Props (IMPORTANT)

- See students portal




## Events 

(see students portal)



## Exercise: buttons to change theme

2 buttons:
- "switch to light theme"
- "switch to dark theme"

How we can solve it (think with students)
- we can have `<div className="light">` and `<div className="dark">`
- it is information that changes over time + we want to reflect it in our JSX -> we will need state
- where we should store it (easiest option atm is in `App.js`)


Question: 
- can we just not change a "normal" variable (ie. do we need state?)
- doesn't it switch back to the initial value



## BEFORE BREAK

- Start next app with CRA
  `npx create-react-app popcorn-time`



## EXTRA

- Mention: in a component we can have multiple stateful variables

- Functional update:
  - Why should I use a function if the new state depends on the previous? Example: https://stackoverflow.com/a/57828519/11298742


