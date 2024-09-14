
# React  Lifting State Up

<!-- 

Status: draft

Note:
- All based on the app "popcorn-time" we created the day before


@todo:
- create diagram(s) with component structure

-->






## Communication from Child to Parent component

Slides (some diagrams with the component hierarchy that we have):
- https://docs.google.com/presentation/d/1EFnNJ6qYZslidhHPM-efifwg_hAqQwndwsdHx3vZ1pI/edit?usp=sharing




Practice: extract code to a child component

<!--
@todo:

Need to  improve instructions for this activity
- goal of Movie component: display the details of only one movie (it will receive those details through props).
- keep the import for .json in MovieList.js

IF NOT, do codealong (instead of class activity)

-->

0. Make sure you have the app running.
  - If you don't have it ready (ex. if it has bugs or different patterns): fork + clone + npm install + npm run dev

Note: before you start making changes, you may want to make a commit (in case you need to discard changes).

1. Create a Movie component (will display a summary with the details of a movie)
  <!-- Movie => MovieSummary -->
2. Modify MovieList.js so that now it renders the Movie component
  - At the end of this iteration, you should be able to see the list of movies
  - Note: for the delete button, you can remove or comment the onClick event (otherwise it will give you an error).
3. Functionality to delete will not work. Try to understand why + try to fix it.


How: in pairs
Time: 30m.


Hints for Iteration 3: 
- Buttons to delete are now in `Movie` component
- When the user clicks on the button, we need to update state in the parent component (we need to update the list of movies, which is stored as state in the `MovieList` component).
- To solve it, we need communication from the child to the parent component.
- You can have a function in the parent component (ex. deleteMovie) and send a reference to that function as props. Then, the child component can invoke that function to update state in the parent component.


Bonus (note: if you do any bonus, avoid modifying the hierarchy of components):
- display "genres"
- research: JSX spread attributes (ex. `<Movie {...movieObj}>`)
- add button "order by rating ascending" / "descending"
- improve CSS


LT:
- show code with steps 1 & 2 solved
  - show syntax props object destructuring
  - show syntax JSX spread attributes (`<Movie {...movieObj}>`)
- solve step 3 together.
      

## Fix Delete functionality (Passing callbacks)


- We need to pass a callback to the child component


  <!-- 
  
    Note:
    - for the callback, can call it  <Component callbackDoSomething={} />
    - also, many students find it easier if we pass the updater function directly to the children (instead of passing a reference to a function in the parent component)
    
  -->



## Display number of movies in the Header component

- Step 0 (in case we we haven't done it yet). 
  - Display number of movies in `MovieList.js`
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


Fix: functionality to delete movie (passing callbacks to grandchild)



## Extra challenges:

- Improve CSS
- Research: JSX spread attributes (ex. `<Movie {...movieObj}>`)

- Add 2 buttons: "Sort by rating ascending" + "Sort by rating descending"
- Add 2 buttons: "Sort by year ascending" + "Sort by year descending"
- Add "Reset" button (clears all filters & resets movies to the original list of movies)


