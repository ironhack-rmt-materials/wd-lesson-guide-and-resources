
# React  Lifting State Up

<!-- 

Status: draft

Note:
- All based on the app "popcorn-time" we created the day before


@todo:
- create diagram(s) with component structure

-->






## Communication from Child to Parent component

<!-- Slides (WIP): https://docs.google.com/presentation/d/1EFnNJ6qYZslidhHPM-efifwg_hAqQwndwsdHx3vZ1pI/edit?usp=sharing -->




Practice: extract code to a child component

<!--
@Luis:

Need to  improve instructions for this activity
- goal of Movie component: display the details of only one movie (it will receive those details through props).
- keep the import for .json in Main.js

IF NOT, do codealong (instead of class activity)

-->

0. Make sure you have the app running.
  - If you don't have it ready (ex. if it has bugs or different patterns): fork + clone + npm install + npm run dev

Note: before you start making changes, you may want to make a commit (in case you need to discard changes).

1. Create a Movie component (will display the details of a movie)
2. Modify Main.js so that now it renders the Movie component
  - At the end of this iteration, you should be able to see the list of movies
  - Note: for the delete button, you can remove or comment the onClick event (otherwise it will give you an error).
3. Functionality to delete will not work. Try to understand why + try to fix it.


How: in pairs
Time: 30m.


Hints for Iteration 3: 
- Buttons to delete are now in `Movie` component
- When the user clicks on the button, we need to update state in the parent component (we need to update the list of movies, wich is stored as state in the `Main` component).
- To solve it, we need communication from the child to the parent component.
- You can have a function in the parent component (ex. deleteMovie) and send a reference to that function as props. Then, the child component can invoke that function to update state in the parent component.


Bonus (note: if you do any bonus, avoid modifying the hierarchy of components):
- display "genres"
- research: JSX spread attributes (ex. `<Movie {...movieObj}>`)
- add button "order by rating ascending" / "descending"
- improve CSS


LT:
- show code with steps 1 & 2 solved
  - show sytax props object destructuring
  - show sytax JSX spread attributes (`<Movie {...movieObj}>`)
- solve step 3 together.
      

## Fix Delete functionality (Passing callbacks)


- We need to pass a callback to the child component


  <!-- 
  
    @Luis:  
    - for the callback, can call it  <Component callbackDoSomething={} />
    - also, many students find it easier if we pass the updater function directly to the children (instead of passing a reference to a function in the parent component)
    
  -->



## Display number of movies in the Header component

- Step 0 (in case we we haven't done it yet). 
  - Display number of movies in `Main.js` (according to the filter criteria)
  - Note: many students solve it adding a new stateful variable (introduce the concept of "SINGLE SOURCE OF TRUTH")

- Step 1:
  - Discuss: what we need to do if we had to display this message in the <Header />
    - (we will need to "lift state up").



## Lift state up

- store list of movies in App.js
- Move controls to App.js as well
  - don't create a specific component for now (we will do that later)
  - Now we can pass the list of movies to <Header />

IMPORTANT:
- Lift state: move to the closest ancestor
- https://reactjs.org/docs/lifting-state-up.html

> Often, several components need to reflect the same changing data. We recommend lifting the shared state up to their closest common ancestor. 


Fix: functionalty to delete movie (passing callbacks to grandchild)



## Extra challenges:
- Add further controls
  - Reset button (clears all filters & resets movies to the original list of movies)
  - Filter movies that are released before/after a year (we still haven't seen forms but you can provide one button for a specific year, ex: "Show old movies (released before 2000)")
  - Sort movies by year (one button)
  - Sort movies rating (one button)

