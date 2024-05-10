
# w4d3


<!-- 

- Continue working on "popcorn-time"

- UPDATE: before routing, do "Lifting State Up"
  - Display number of movies in the header

- todo: add quick exercise with routing

-->




## Day Planning
 
- LAB Q&A [20m]

- Optional: solve Bonus iteration 4 
  - "Bonus: Iteration 4 | Extract Component"
  - Solve it on the app "popcorn-time"
    - extract movie details to `Movie` component
    - Note: will need to pass a function as props.

- Refresh [30m]
  - see below


- ~~Destructuring Assignment~~ [30m]


- Examples of routing: 
  - https://meet-them-all.netlify.app/
  - https://wordrobe-wonderland.netlify.app
  - airbnb
- Routing intro [1h]
- Routing advanced - url params [1h]
- Routing advanced - query string [10m]
  - (just some notes / show cheatsheet) 
  - In lab "React Cohort Tools": not needed (as of may24)
  - In lab "React Stack Tracker" it's a bonus iteration.



## Active Learning

- (individual) LAB | React Cohort Tools

- (in pairs) Mini Project | React App (Day 3)

- Bonus: 
  - LAB | React Stack Tracker




## Refresh

- props vs. State:

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

- Refresh syntax useState()

- Remember:
  - NEVER MODIFY STATE DIRECTLY 
  - State Updates May Be Asynchronous

- .map()

- Conditional rendering

