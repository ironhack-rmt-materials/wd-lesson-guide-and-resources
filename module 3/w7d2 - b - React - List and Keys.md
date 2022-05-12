
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
    - time: 15 + 10min
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
  - Make initial commit & upload to GitHub
  
  - Create 3 function components: <Header /> <Main /> <Footer />
    (for each of them, just display a text, ex: "this is the header")

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


  - Create an array with the details of 3 movies
    - Why: this information may come from the DB or from an API

    ```
    const moviesArray = [
        {
            id: 1,
            title: "",
            rating: ""
        }
    ]
    ```
    

    - Display the list of movies, from the array

    ```
    {moviesArray.map( movie => {
        return <div>Title: {movie.title}</div>
    })}
    ```

    - See Warning in the console: we need to add "key" prop


    - Load list of movies from a `json` file
      <!-- Extra: can ask students to remove the code we did before, so that the can practice with .map() again -->
      - IMPORTANT: explain how to load data from a json file (they will do it in LAB react-ironcontacts)
      - Sample json file: https://github.com/Ironborn-Ironhack-March-2022/react-popcorn-time/blob/main/src/data/movies.json



    - Instead of a div, create a `<Movie />` component
      - this component will display the title of a movie.
      - From Main.js, render 3 times the Movie component, with different titles (pass the title as props)


    - (bonus for advanced students)...
      - display rating & image
      - add style for Movie
      - display genres (need .map() inside Movie)


    - Conditional Rendering
      - Intro: refresh ternary operator
      - Explain (see React docs)
      - Examples:
        - if rating > 8 display a text "RECOMMENDED"
        - (bonus) if rating > 8 apply a different background (hint: `className`)
        - if imgURL not  available, display placeholder image



    - Save the array in the state of the <Main> component
        - Extra: implement a button to display only movies with rating > 8
           - If the information about movies to display changes over time.
        - Extra: add button to sort by rating
        - Extra: implement a button to delete a movie from the list
        `<button onClick={props.clickToDelete}>Delete</button>`


    - Extras (before them, explain conditional rendering):     
        - Extra: JSX spread attributes.
          - `<Movie {...movieObj}>`
      
