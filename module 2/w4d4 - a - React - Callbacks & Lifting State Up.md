
# React: Callbacks & Lifting State Up


<!--

Note: we will continue working on the app from yesterday, `popcorn-time`.

-->




## Intro: explain React callbacks

Initial code (just a Child component): 
- https://stackblitz.com/edit/react-1wdmbggs?file=src%2FApp.js


Step 1:
- In App.js: create a state variable: `counter`
- In App.js: create a function to increment the counter: `increment`

```jsx
  const [counter, setCounter] = useState(0);

  const increment = () => {
    setCounter(counter + 1);
  };
```

Step 2:
- We want to invoke that function from the Child component...
- Refresh: how to pass props (e.g. pass as props `message="hello world"`)
- Implement with a callback

Final result: 
- https://stackblitz.com/edit/react-2un9kte8?file=src%2FApp.js



## Practice: React callbacks

Initial code: https://stackblitz.com/edit/vitejs-vite-ptv4u3dn?file=src%2FApp.jsx

Iteration 0:
- Read and understand the code in `App.jsx`
- Read and understand the code in `Child.jsx`

Iteration 1:
- Implement the functionality so that, when the user clicks on the button, it will double the value in the counter.

- Hints (in case you need it):
  - The button is located in `Child.jsx`. However, the counter state and logic to update it are in `App.jsx` (ie. from `Child.jsx`, you need to invoke a function in `App.jsx`)
  - When you render the child component, you will need to pass a callback (example: `<Child myCoolCallback={doSomething} />`).
  - In Child.jsx, receive the props and invoke the callback when the button is clicked (example: `onClick={props.myCoolCallback}`) 

Bonus 1: Add another button in Child.jsx to reset the counter to 1.
Bonus 2: Disable the button in Child.jsx if the counter goes above a certain value (e.g. 100).

Time: 15min.


Solution: https://stackblitz.com/edit/vitejs-vite-pvvydcgk?file=src%2FApp.jsx

Solution bonus 1: https://stackblitz.com/edit/vitejs-vite-pvvydcgk?file=src%2FApp.jsx

Solution bonus 2: https://stackblitz.com/edit/vitejs-vite-rcead9fk?file=src%2FApp.jsx




## Refactor: extract movie details to a separate component


Note: for the next steps, we will continue working on the app from yesterday, `popcorn-time`.


Motivation:
- As our components get more complex, sometimes you want to split the code in smaller pieces.
- In this case, we will extract the details of a movie to a specific component.

<!-- 

Note:
- This is equivalent to step 5 in the mini-project ("React App - Day 2")

> Make the list item a separate component and use the new component to render the list items (for example, <ListItem /> or <ItemCard />).

-->


Steps:
- Create the component `MovieSummary` (will display the details of a movie)
- Modify `MovieList.jsx` so that now it renders the MovieSummary component
- Note: For now, comment the button to delete (we'll fix it a bit later)


Slides (some diagrams with the component hierarchy that we have):
- https://docs.google.com/presentation/d/1EFnNJ6qYZslidhHPM-efifwg_hAqQwndwsdHx3vZ1pI/edit?usp=sharing



## Fix: functionality to Delete (passing callbacks)

- We need to pass a callback to the child component


<!-- 

Note: for the callback, start by call it <Component callbackDoSomething={} />
  
-->



## Display number of movies in the Header component

- Step 0 (in case we we haven't done it yet). 
  - Display number of movies in `MovieList.js`
  - Note: many students solve it adding a new stateful variable (introduce the concept of "SINGLE SOURCE OF TRUTH")

- Step 1:
  - Discuss: what we need to do if we had to display this message in the <Header />
    - (we will need to "lift state up").



## Lift state up

- Store list of movies in App.jsx
- Now we can pass the list of movies to <Header />


Explain:
- Lift state: move to the closest ancestor
- https://reactjs.org/docs/lifting-state-up.html

> Often, several components need to reflect the same changing data. We recommend lifting the shared state up to their closest common ancestor. 


Fix: functionality to delete movie (passing callbacks to grandchild)



## Extra challenges:

- Improve CSS
- Research: JSX spread attributes (e.g. `<Movie {...movieObj}>`)

- Add 2 buttons: "Sort by rating ascending" + "Sort by rating descending"
- Add 2 buttons: "Sort by year ascending" + "Sort by year descending"
- Add "Reset" button (clears all filters & resets movies to the original list of movies)


