
# w7d3

<!-- 

Notes:
- We will work on the app "popcorn-time" we created the day before
- React Forms can take much longer than it seems (about 4h)

LAB today ("React IronNutrition") is VERY VERY demanding
- try to finish earlier so that they have more time
- offer students the possibility to work in pairs
- give extra guidance for first iterations


-->


## Quick lab review

Ask students for yesterday's LAB (specific questions)



## Refresh


State:

- State vs. props.

- When should we use the state
  - Store information that belongs to a component
  - Can change over time
  - We want to reflect the changes in the UI (JSX)

- Syntax
  - hooks
  - useState() hook

- Remember:
    - Do Not Modify State Directly
        - Instead, use the updater function (ex. `setCounter`)
    - State Updates May Be Asynchronous
        - If new state depends on prev state, we pass a funcion
        (ex. `setCounter( () => {})`)

- Also remember...
    - "Data Flows Down"
      - A component may choose to pass its state down as props to its child components
      - https://reactjs.org/docs/state-and-lifecycle.html#the-data-flows-down


Lists
- .map()
- https://reactjs.org/docs/lists-and-keys.html

  <!--
  @Luis:
  - ex. refresh .map() on react-playground with `<Movie />`
  -->



Conditional rendering
- https://reactjs.org/docs/conditional-rendering.html


Show the app we were building yesterday
- list of movies loaded from `json`
- in most apps, it would come from an API



## Today

Popcorn Time II...

Lifting state up:
- extract Controls or Movie to a specific component (communication child-parent, now we need to pass a callback to the child component) 
- Display number of movies (in the same component where we have the list)
- Display number of movies in the header (Lifting state up)
- functionality to filter based on minRating (passing arguments in the callback)


Forms:
- functionality to add movies (Step 1: form with 1 field)
- functionality to add movies (Step 2: form with multiple fields)
- functionality to add movies (Step 3: extract to a separate component)
- (extra) Handling multiple inputs with a single method


Extra:
- functionality for searchbox (asked in today's lab)
