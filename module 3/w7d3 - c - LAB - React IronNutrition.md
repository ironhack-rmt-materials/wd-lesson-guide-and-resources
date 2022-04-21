

# LAB - React IronNutrition

Main topics:
- State
- Form (controlled components)
- Communication between components (props, callback)



## Remember that React may not update state immediately.

Example, with the searchbar:

  ```javascript
    const [searchInput, setSearchInput] = useState("");
    
    function inputHandler(e) {
        setSearchInput(e.target.value);  
        updateMyList(searchInput);   // we're passing "searchInput", which is in state.
    }
  ```

That may not work as expected (to filter foods, we had to type always one letter more than expected).

Why: we are using a variable from state (searchInput) immediately after asking React to update it.

Posible Solution:

  ```javascript
    const [searchInput, setSearchInput] = useState("");

    function inputHandler(e) {
        setSearchInput(e.target.value);
        updateMyList(e.target.value); // we use an up to date value
    }
  ```

Note: tomorrow we will learn useEffect() which can be useful.

