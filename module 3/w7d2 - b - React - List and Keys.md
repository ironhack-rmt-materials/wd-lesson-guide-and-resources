
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
  
  - refresh forEach() & map()
  - Important difference: 
    - forEach() will return undefined
    - map() returns an array


- Intro:
  - So far we have been displaying list of things
  - but we are not storing this information in a specific data structure (eg. an array of recipes)


- Codealong:
  - Make initial commit & upload to GitHub
  - Create components: <Header /> <Main /> <Footer />
  - In Main, create 3 divs with a movie
  - Put those 3 divs in an array and show how it is possible to display an array

    ```
    const list = [
      <div>one</div>, 
      <div>two</div>, 
      <div>three</div>
    ];
    
    // ....
    
    {list}
    ```

  - Create an array with the details of each movie
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

    - Instead of a div, create a component <Movie>
    - Pass the info as props
    


    - Extras (before them, explain conditional rendering):     
        - Extra: JSX spread attributes.
        `<Movie {...movieObj}>`
        - Extra: save the array in the state of the <Main> component
        - Extra: implement a button to display only movies with rating > 8
        - Extra: implement a button to delete a movie from the list
        `<button onClick={props.clickToDelete}>Delete</button>`

    - IMPORTANT: explain how to load data from a json file (they will do it in LAB react-ironcontacts)
      - Sample json file: https://github.com/Ironhack-Team-Triangle-July2021/ironhack-cinema/blob/main/src/data/movies.json


