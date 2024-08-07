
# w7d3




<!-- 

- Continue working on "popcorn-time"

- UPDATE: before routing, do "Lifting State Up"
  - Display number of movies in the header

- todo: add quick exercise with routing

-->


<!-- 

@todo: IMPROVE / SIMPLIFY 
- remove anything not essential
- first, introduce the concept (ex. with slides) & then see how to apply it (demo) ?
  - ex. 
    - passing a callback as props
    - lifting state up
    - forwarding props to grandchild
    - ...


@update:
- Main => MovieList
- Movie => MovieSummary



Notes:
- We will work on the app "popcorn-time" we created the day before

LABs today are VERY VERY demanding
- try to finish earlier so that they have more time

-->


## Refresh

- (skip) Routing cheatsheet
  - setup
  - basic routing
  - url params


Show the app we were building yesterday
- list of movies loaded from `json` (in most apps, it would come from an API)
- component hierarchy (see react dev tools + see code)





## Planning A

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




## Planning B

Popcorn Time II...

Lifting state up [~~3h~~] [1.5h]
- (skip) Create a Movie component (will display the details of a movie)
  <!-- Nope, do not create Movie component  -->
- Display number of movies in the Header component (Lifting state up)
  - Fix Delete functionality (Passing callback to grandchild)


Forms: [2.5h]
- functionality to add movies (Step 1: form with 1 field)
- functionality to add movies (Step 2: form with multiple fields)
  - as an exercise (see "React - Forms.md")
- fix: routing (generate unique id's)
- (extra) functionality to add movies (Step 3: extract to a separate component)
- (extra) Handling multiple inputs with a single method


Extra:
- functionality for searchbox (asked in today's lab)




## Refresh

- props vs. State:

    - When should we use the PROPS:
    - Pass information to a child component
    - ex. reusable component that has different behavior depending on info that it receives.

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




## Active Learning

- (individual) LAB | React Cohort Tools

- (in pairs) Mini Project | React App (Day 3)

- Bonus: 
  - LAB | React Stack Tracker


