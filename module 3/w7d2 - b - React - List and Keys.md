
# React - List and Keys

<!-- 

Status: draft

@Luis: 
- This unit has improved a lot with v6.1
- Consider following steps students portal instead (do "popcorn-time" but follow steps from this unit, so that students understand the logical process)

-->


- START BUILDING
  `npx create-react-app popcorn-time`


- Meantime... Warmup exercise with arrays:
  https://stackblitz.com/edit/ih-react-exercise-with-arrays?file=index.js
  
  - How:
    - can be in pairs
    - time: 15m
  - Goals:
    - refresh forEach() & map()
    - Important difference: 
      - forEach() will return undefined
      - map() returns an array


  - Solve together:
    - map vs filter vs reduce: https://miro.medium.com/max/880/0*cQwPe6QPdl_-ByOq.png

  - Possible solution: https://stackblitz.com/edit/ih-react-exercise-with-arrays-x6ewcz?file=index.js
    



- Intro:
  - So far we have been displaying list of things
  - but we are not storing this information in a specific data structure (eg. an array of recipes)


- Codealong:

  <!-- 
  @Luis: can ask students to do the first 3 steps (15min) 
  -->

  - Upload repo to GitHub
  
  - Run the app

  - Create 3 function components: 
    - Header, Main, Footer
    - for each of them, just display a text, (ex: "this is the header").


  - (extra) style: css file for a component
    - create `Header.css`
    - in Header component:
      - `import "./Header.css";`
    - NOTE: any css rules would apply to the whole application
      - in the component add `<header className="Header">`
      - in the css, add the class to all rules
        - ex: https://github.com/Ironborn-Ironhack-March-2022/react-popcorn-time/blob/main/src/components/Header.css



  - Inside <Main />, create 3 divs with a movie
    ```javascript
      <div className="Main">

        <div>movie one</div>
        <div>movie two</div> 
        <div>movie three</div>

      </div>
    ```

  - Put those 3 divs in an array and show how it is possible to display an array

    ```javascript
    const list = [
      <div>movie one</div>, 
      <div>movie two</div>, 
      <div>movie three</div>
    ];
    
    // ....
    
    {list}
    ```

  - TAKEOVER: in JSX, we can render an array of elements (those elements can be html or any valid JSX)

  - Create an array with the details of 3 movies
    - Why: this information may come from the DB or from an API

    ```js
    const moviesArray = [
      {
        "id": 1,
        "title": "The Godfather",
        "rating": 9
      },
      {
        "id": 2,
        "title": "Forrest Gump",
        "rating": 9
      },
      {
        "id": 3,
        "title": "Gladiator",
        "rating": 8
      },
    ]
    ```
    

    - Display the list of movies, from the array
      - IMPORTANT: do not create a specific component

      <!-- 
      @Luis: 
        - Keep everything inside the Main component 
        - (do not create a specifi component!)
      -->


      ```js
      {moviesArray.map( movie => {
          return <div>Title: {movie.title}</div>
      })}
      ```

    - See Warning in the console: we need to add "key" prop
      - NOTE: use the `index` as key (tomorrow we will have functionality to add new movies, we don't want to ask the user for the id)
      > "When you don’t have stable IDs for rendered items, you may use the item index as a key as a last resort"


    - Load list of movies from a `json` file
      - create `data/movies.json`
      - Sample json file: https://github.com/Ironborn-Ironhack-March-2022/react-popcorn-time/blob/main/src/data/movies.json
      - (Extra) ask students to remove the code we did before, so that the can practice again with .map()



  - Removing elements from a list (see students portal)
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


  - (extra challenges)...
    - display year & image
    - add style for Main component
    - display genres (note: it's an array)


  - (Extra) display a title with the number of movies 
    - ex. `<h1>We have {movies.length} movies available</h1>`
    - IMPORTANT: display that in the `<Main>` component !!!
    - NOTE: many students solve it adding a new stateful variable (introduce the concept of "SINGLE SOURCE OF TRUTH")

  - Conditional Rendering
    - Intro: refresh ternary operator
    - Explain (see React docs)
    - Examples:
      - (`Element Variables`) if there's zero movies, display a different message
      - (`Logical && Operator`) if rating > 8 display a text "RECOMMENDED"
      - (`Ternary Operator`) if imgURL not  available, display placeholder image
      - (bonus) if rating > 8 apply a different background (hint: `className`)



  - (skip) Instead of a div, create a `<Movie />` component
      - this component will display the title of a movie.
      - From Main.js, render the Movie component (pass the title as props)
      <!-- @Luis: skip this (we haven't seen comunication from child to parent component + they don't need it for today's lab) -->



  - (Extra challenges):
    - Implement a button to display only movies that have rating > 8
    - Add button to sort by rating
    - Add favIcon
      - Can use these images: https://github.com/Ironhack-Team-Triangle-July2021/ironhack-cinema/commit/f4cf21c91608b1fdf95b359031e676c90cbf8c3f#diff-09e657b7706f48b0af84577d8d340912648fa2d247d808a18e26e3459df1a26b

  - Extra: JSX spread attributes.
    - `<Movie {...movieObj}>`
      

