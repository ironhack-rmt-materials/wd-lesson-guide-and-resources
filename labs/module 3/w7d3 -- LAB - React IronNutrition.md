# LAB LAB - React IronNutrition

[REPO](https://github.com/ironhack-labs/lab-react-ironnutrition)

[SOLUTION](https://gist.github.com/TA-Remote/c09007c6ba56c8335bdaa7512b975acf)

<!-- Trying to update the info -->

## Iteration 0 - Setup

### 1. Install Ant Design (css framework)

```cli
  $ npm install antd --save
```

### 2. import antd to the index.js and foods.json to App.js

```javascript
  import 'antd/dist/antd.min.css';
  import foods from './foods.json';
```

---

## Iteration 1 - FoodBox

### 1. create new FoodBox.js component

-> create components folder and create file FoodBox.js

### 2. return the given html from instructions to render food

### 3. import FoodBox component into App.js and render in return

```javascript
  import FoodBox from './components/FoodBox';
```

```javascript
  return <FoodBox />
```

---

## Iteration 2 - Display foods from json

### 1. use props in FoodBox.js component

-> change values accordingly (check json file for keys) - for example:

```javascript
  <img src={props.image} alt={props.name} />
```

## Iteration 3 - Render a List of FoodBox Components

### 1. in App.js use .map() method to render all foods from json

-> (no state neccessary here)

```javascript
   {foods.map((food) => {
   return (
   <FoodBox
      name={food.name}
      calories={food.calories}
      image={food.image}
    />
   );
   })}
```

---

## Iteration 4 - Add new food form

### 1. create new AddFoodForm.js component

### 2. create onSubmit-Form with all input values (name, image, calories, servings)

```javascript
  <div class="AddFoodForm">
    <div className={isHide ? 'show' : 'hide'}>
      <form onSubmit={submitButton}>
        <label>Name:
          <input
            name="name"
            value={addedFood.name}
            type="text"
            onChange={handleInputChange}
          />
        </label>
        
        <label>Image:
          <input
            name="image"
            value={addedFood.image}
            type="text"
            placeholder="https://via.placeholder.com/30x30"
            onChange={handleInputChange}
          />
        </label>

        <label>Calories:
          <input
            name="calories"
            value={addedFood.calories}
            type="number"
            onChange={handleInputChange}
          />
        </label>

        <button type="submit" id="buttonCreate">
          Create
        </button>
      </form>
    </div>
  </div>
```

### 3. create useState for addedFood with initial states for these values (empty strings)

```javascript
   const [addedFood, setAddedFood] = useState({
   name: '',
   image: '',
   calories: '',
   servings: '',
   });
```

### 4. create function to handleInputChange (important call setAddedFood)

--> all fields with onChange

```javascript
   const handleInputChange = (event) => {
   const value = event.target.value;
   setAddedFood({ ...addedFood, [event.target.name]: value });
   };
```

### 5. create function for submitButton and define function handleSubmit as props to App.js

```javascript
const submitButton = (event) => {
props.handleSubmit(event, addedFood);
};
```

## // Lift up to App.js

### 10. import AddFoodForm.js to App.js

```javascript
  import AddFoodForm from './components/AddFoodForm';
```

## 11. add useState to change rendered FoodsList

```javascript
  const [foods, setFoods] = useState(foodsList);
```

## 12. add function handleSubmit (for props from AddFoodForm)

```javascript
    const handleSubmit = (event, newFood) => {
    event.preventDefault();
    const updateFood = [newFood, ...foods];
    setFoods(updateFood);
    };
```

## 13. add AddFoodForm.js component in return to render

```javascript
  <AddFoodForm handleSubmit={handleSubmit} />
```

## 14. change the array that uses .map()

-> now we not tell to render foodsList from json only, but also the added food
-> so use foods from state

```javascript
  foods.map()
```

---

## Iteration 5 - Search

### 1. add state for filteredFoods

```javascript
  const [filteredFoods, setFilteredFoods] = useState('');
```

### 2. add function handleSearchInput

```javascript
  const handleSearchInput = (event) => {
    setFilteredFoods(event.target.value);
  };
```

### 3. add searchbar html

-> add input field in return of App.js (no need to create extra component)

```javascript
  <div className="Searchbar">
    <input
      value={filteredFoods}
      placeholder="Search food"
      type="text"
      onChange={handleSearchInput}
    />
  </div>
```

### 4. change your foods.map()

-> filter before map + iternary operator for when foodsList = 0)
-> when filter make it case-insensitive with toLocaleLowerCase()

```javascript
  {foods.length === 0 
    ? 
    <h1>Oops! There is no more content to show</h1>
    :
    foods
      .filter((food) => {
        const lowerFilter = filteredFoods.toLocaleLowerCase();
        return food.name.toLocaleLowerCase().includes(lowerFilter);
      })
      .map((food, index) => {
        return (
          <div key={index}>
            <FoodBox
              name={food.name}
              calories={food.calories}
              image={food.image}
            />
          </div>
        );
      })
  }
```

## Iteration 6 - Create a delete button

## BONUS Iteration 7 - Hide Form

### 1. add useState to change isHide state

-> set initial state to 'false'

```javascript
const [isHide, setIsHide] = useState(false);
```

### 2. create function to hide/show form in button

-> setIsHide function will always do what is different the current state (!isHide)

```javascript
  const handleHide = () => {
    setIsHide(!isHide);
  };
```

## 3. add property in App.css with class with default not displayed

```javascript
  .hide {
    display: none;
  }
```

## 4. add div around Form with className

-> use iternary to change className

```javascript
  <div className={isHide ? 'show' : 'hide'}>
```

<!-- That is from the older version of the lab -->
## Iteration 5 - Create add-button // Todays Food

### 1. Create new State

-> state with empty array

```javascript
  const [todaysFoods, setTodaysFoods] = useState([]);
```

### 2. Create handleAddFood function in App.js

-> function to add value to todaysFood, when clicking on add-button

```javascript
 const handleAddFood = (addedFood) => {
    setTodaysFoods((prevTodaysFood) => [addedFood, ...prevTodaysFood]);
  };
```

### 3. Pass down handleAddFood into child component FoodBox.js

```javascript
  <FoodBox food={food} onAddFood={handleAddFood} />
```

### 4. Inside FoodBox.js

--> add onClick event on button(+); through onClick we sending the updated food object with new amount from input field

```javascript
 <button
   onClick={() => {
   props.onAddFood({
      food: food,
      amount: amount,
   });
   }}
  >
```

--> create state to hold amount

```javascript
 const [amount, setAmount] = useState(1);
```

--> create function to handle amount input field

```javascript
 const handleChangeAmount = (event) => {
    setAmount(event.target.value);
  };
```

### 5. in App.js - Iterate through todaysFoods array to display amount, name, calories

-> Hint: display correct quantity after adding foods

Overall, well done Ha Thu!
Just minor suggestions (see above);

As a hint to hide the "AddFood"-Form:
-> add a state, so you can change if hide or shown

```javascript
  const [isHide, setIsHide] = useState(false);
```

-> Wrap a div around whole form:

```javascript
  <div className={isHide ? 'show' : 'hide'}>
  ...
  </div>
```

-> write function to handle this state:

```javascript
  const handleHide = () => {
   setIsHide(!isHide);
  };
```

-> add these html in your return:

```javascript
  <button id={isHide ? 'hide' : 'show'} onClick={handleHide}>
    {isHide ? 'Hide' : 'Show'}
  </button>
```

-> at least define a class in your CSS

```javascript
  .hide {
  display: none;
  }
```




