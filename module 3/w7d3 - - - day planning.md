
# w7d3

<!-- 



Today:
- DEMO (instead of codealong)
- @todo: prepare quick exercises (stackblitz/codesandbox)



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

- props vs. State

- When should we use the PROPS:
  - Pass information to a child component
  - ex. reusable component that has different behaviour depending on info that it receives.

- When should we use the STATE:
  - Store information that belongs to a component
  - Can change over time
  - We want to reflect the changes in the UI (JSX)


- A Component will Re-render if:
  - receives new props from the outside
  - its own state changes


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
- Cheatsheet: https://gist.github.com/luisjunco/7eab10cd2991fab11a759add4a15b7cc


Show the app we were building yesterday
- list of movies loaded from `json`
- in most apps, it would come from an API



## Today

Popcorn Time II...

Lifting state up [3h]
- Create a Movie component (will display the details of a movie)
  - Fix Delete functionality (Passing callbacks)
- Display number of movies in the Header component (Lifting state up)
  - Fix Delete functionality (Passing callback to grandchild)


Forms:
- functionality to add movies (Step 1: form with 1 field)
- functionality to add movies (Step 2: form with multiple fields)
- functionality to add movies (Step 3: extract to a separate component)
- (extra) Handling multiple inputs with a single method


Extra:
- functionality for searchbox (asked in today's lab)
