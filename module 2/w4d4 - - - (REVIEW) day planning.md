
# w7d3




<!-- 

- Continue working on "popcorn-time"
- Consider: isolate each topic (working on different apps to keep things simple)


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

-->


## Refresh

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

- Examples of routing: 
  - https://brews-and-bites.netlify.app/
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


