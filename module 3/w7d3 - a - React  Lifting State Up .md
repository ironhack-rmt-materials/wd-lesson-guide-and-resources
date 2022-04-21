
# React  Lifting State Up

<!-- 

Status: draft

Note:
- All based on the app "popcorn-time" we created the day before

-->


## Warmup Exercise


In our popcorn-time app:

- Iteration 1. 
  - Implement functionality to display number of movies that meet the filter criteria 
  - note, we can display this message between the filters & the list of movies (<Main />).

- Iteration 2:
  - Discuss: what we need to do if we had to display this message in the <Header />


  <!--

  notes:
  - Iteration1: students need to practice what we know (displaying info from state in JSX)
  - Iteration2: we start thinking about "lifting state up"
  -->


## Lift state up

- store list of movies in App.js
- Move controls to App.js as well
  - don't create a specific component for now (we will do that later)
  - Now we can pass the list of movies to <Header />

IMPORTANT:
- Lift state: move to the closest ancestor


## Passing callbacks:

- Move controls to a separate component <Controls />
  - We need to pass a callback to the child component

- How to pass information in the callback to the parent component
  - We can use an anonymous function
  - Ex. 2 buttons to filter for different rating

    ```
      <button onClick={ () => props.displayTop(8) } >Only 8 and above</button>
      <button onClick={ () => props.displayTop(9) } >Only 9 and above</button>
    ```

- (extra) Implement functionality to delete a movie
  - need to pass a callback to grandchild
  - when we execute the callback, we need to pass the id of the movie



## Extra challenges (advanced students):
- Add further controls
  - Reset button (clears all filters)
  - Filter movies that are released before/after a year (one button, ex: "only after 2010")
  - Sort movies by year (one button)
  - Sort movies rating (one button)
