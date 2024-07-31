
# React - List and Keys

<!-- 

Status: draft

@Luis: 
- This unit has improved a lot with v6.1
- Consider following steps students portal instead (do "popcorn-time" but follow steps from this unit, so that students understand the logical process)

-->



## (skip ?) Refresh: working with arrays

<!-- Goal: refresh forEach() & map() -->

- Instructions: https://stackblitz.com/edit/ih-react-exercise-with-arrays?file=index.js
  
- How: solve together / work in pairs
- Time: 15-20min.



- Explain: 
    - forEach() will return undefined
    - map() returns an array


- Solve together:
  - diagram map: https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_c465728a5460c8d562936d4f1b5d18cc.png
  - map vs filter vs reduce: https://miro.medium.com/max/880/0*cQwPe6QPdl_-ByOq.png


- Possible solution (w/o bonus): https://stackblitz.com/edit/ih-react-exercise-with-arrays-vefnrt?file=index.js

- Possible solution with bonus: https://stackblitz.com/edit/ih-react-exercise-with-arrays-3dwodd?file=index.js






## Initial Setup:

- open VS Code + a terminal
- navigate to your module2 directory
- create app with Vite:
  - `npm create vite@latest popcorn-time -- --template react`
- cd popcorn-time
- code -r .
- npm install
- npm run dev
  - In case you need to define a custom port (for example, if you have another app running in your computer): `npm run dev -- --port 3000`

- git init
- initial commit
- upload to github



 
## Practice: Create the initial structure for "popcorn time"


<!-- @LT: if short of time, do as a codealong instead -->

Iteration 0: Cleanup - delete initial code from Vite

Iteration 1: Create the initial structure. 
  - Create 3 function components: Header, MovieList, Footer
  - for each of them, just display a text, (ex: "this is the Header").
  - render all of them in App

  <!-- @update: use MovieList instead of Main -->

Iteration 2: Make a commit + Upload repo to GitHub

Bonus: add some css for the Header component with a specific file
    - create `Header.css` + add rules for `h1` (ex. `color: orange`)
    - in Header.jsx, import the css file you've created: `import "./Header.css";`
    - NOTE: any css rules would apply to the whole application. To avoid this, you can do the following:
      - add a className to the parent html element of your component. Ex: `<header className="Header">`
      - in the css, add the class to all rules
        - ex: https://github.com/Ironborn-Ironhack-March-2022/react-popcorn-time/blob/main/src/components/Header.css


Time: 10min. + solve together.



## (skip) Intro: working with lists (arrays) in React


- What we've done so far

  ```jsx

    const tweetsArray = [];

    // ...

    <Tweet tweet={ tweetsArray[0] }>
    <Tweet tweet={ tweetsArray[1] }>
    <Tweet tweet={ tweetsArray[2] }>

  ```

- We will often work with arrays of objects but this syntax is not flexible enough.
  - eg. if we have an array with 200 elements
  - eg. if we don't know how many elements we will have in the array


- Inside <Main />, create 3 div's with a movie
  <!-- @update: use MovieList instead of Main -->

  ```jsx
    <div className="Main">

      <div>movie one</div>
      <div>movie two</div> 
      <div>movie three</div>

    </div>
  ```

- Put those 3 div's in an array and show how it is possible to display an array

  ```jsx
  const list = [
    <div>movie one</div>, 
    <div>movie two</div>, 
    <div>movie three</div>
  ];
  
  // ....
  
  {list}
  ```


- TAKEOVER: 
  - in JSX, we can render an array of elements (those elements can be html or any valid JSX)



## Quick demo: .map() with an array of strings

Before we import the json file yet, do a quick demo with a plain array:


  ```js

  const movies = ["The Godfather", "The Matrix", "Star Wars"]

  // ...

  {movies.map()}

  ```




## Import json file


Load list of movies from a `json` file
  - create `data/movies.json`
  - Sample json file: https://github.com/Ironborn-Ironhack-March-2022/react-popcorn-time/blob/main/src/data/movies.json
  - Import in Main.js: `import movies from "../data/movies.json";`

  <!-- IMPORTANT: add this in Main.js -->
  <!-- IMPORTANT: add this in Main.js -->
  <!-- IMPORTANT: add this in Main.js -->


- Note: this information will often come from a DB / API




## Display the list of movies, from the array

  - IMPORTANT: do not create a specific component

  <!-- 
  @Luis: 

    - Keep everything inside the Main component 
    - (do not create a specific component!)

    - Can do DEMO (later, when we load from json, I will ask them to do again)

  -->


  ```js
  {moviesArray.map( movie => {
      return <div>Title: {movie.title}</div>
  })}
  ```

- See Warning in the console: we need to add "key" prop
  - NOTE: use the `index` as key (tomorrow we will have functionality to add new movies, we don't want to ask the user for the id)
  > "When you don’t have stable IDs for rendered items, you may use the item index as a key as a last resort"


- (Extra) add some basic css to card "movie"

  ```css
  .Main .card {
    max-width: 80%;
    margin: 1rem auto;
    padding: 1rem;
    border: 1px solid #666;
    box-shadow: 5px 5px 10px -5px;
    transition: 0.4s;
  }

  .Main .card:hover {
      cursor: pointer;
      box-shadow: 5px 5px 10px 0px;
  }
  ```

<!-- commit -->



## Practice: iterate through an array with .map()


Initial code: https://stackblitz.com/edit/stackblitz-starters-2hqmjf?file=src%2Fcomponents%2FMain.js


1. In Main.js, import this json file:
  - `import events from "../data/events.json"`
2. For each element of the array, display the title and the location (use `.map()`)

Time: 10min.

Solution: https://stackblitz.com/edit/stackblitz-starters-knjkk5?file=src%2Fcomponents%2FMain.js




## Removing elements from a list (will apply State)

Initial step:
- add: `<button>Delete this movie</button>`

Discuss: 
- how we can implement functionality to delete movies

Steps:

- Store the List Array in state
- Render the List Array from state
- Delete Button (note: we need to pass the Id of the movie)
  ```jsx
  <button onClick={() => deleteMovie(movie._id)}>
    Delete
  </button>
  ```
- Update state when user clicks on button

```js
  const deleteMovie = movieId => {
    const filteredMovies = movies.filter(movie => {
      return movie._id !== movieId;
    });

    setMovies(filteredMovies);
  };
```

<!-- map vs filter vs reduce: https://miro.medium.com/max/880/0*cQwPe6QPdl_-ByOq.png -->



## (extra challenges)...
  - display year & image
  - display genres (note: it's an array)
  - in Main.jsx, display a title: `<h1>We currently have XXX movies available</h1>`



## Display a title with the number of movies 

<!--
@Luis: 
- do this today (will help so that tomorrow we intro "lifting state up")
- IMPORTANT: display in the same component where we have the list of movies (ex. Main.js)
-->

  - ex. `<h1>Number of movies: {movies.length}</h1>`
  - IMPORTANT: display that in the `<Main>` component !!!
  - NOTE: many students solve it adding a new stateful variable (introduce the concept of "SINGLE SOURCE OF TRUTH")


