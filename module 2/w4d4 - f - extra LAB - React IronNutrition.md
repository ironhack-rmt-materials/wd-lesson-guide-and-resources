

# LAB - React IronNutrition


How:
- in Pairs



Notes: 
- students find this lab VERY challenging

Main topics:
- Component Libraries (Ant Design)
- State
- Form (controlled components)
- Communication between components (props, callback)



## Iteration 0 | Setup

- We will use a component library (Ant Design)



## Remember that React may not update state immediately.

Example, with the searchBar:

  ```js
    const [searchInput, setSearchInput] = useState("");
    
    function inputHandler(e) {
        setSearchInput(e.target.value);  // please, when you can.... update state
        updateMyList(searchInput);   // we're passing "searchInput", which is in state.
    }
  ```

That may not work as expected (to filter foods, we had to type always one letter more than expected).

Why: we are using a variable from state (searchInput) immediately after asking React to update it.

Possible Solution:

  ```js
    const [searchInput, setSearchInput] = useState("");

    function inputHandler(e) {
        setSearchInput(e.target.value);
        updateMyList(e.target.value); // we use an up to date value
    }
  ```

Note: tomorrow we will learn useEffect() which can be useful.

