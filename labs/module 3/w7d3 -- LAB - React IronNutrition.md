# LAB LAB - React IronNutrition

[REPO](https://github.com/ironhack-labs/lab-react-ironnutrition)

[SOLUTION](https://gist.github.com/TA-Remote/c09007c6ba56c8335bdaa7512b975acf)

<!-- outdated intro  -->

## Iteration 0 - Setup

### 1. Install bulma (css framework)

```
$ npm install bulma --save
```

### 2. import bulma and foods.json to App.js

```
import 'bulma/css/bulma.css';
import foodsList from './foods.json';
```

---

## Iteration 1 - FoodBox

### 1. create new FoodBox.js component

-> create components folder and create file FoodBox.js

### 2. return the given html from instructions to render food

### 3. import FoodBox component into App.js and render in return...

```
import FoodBox from './components/FoodBox';
```

```
return <FoodBox />
```

---

## Iteration 2 - Display foods from json

### 1. use props in FoodBox.js component

-> change values accordingly (check json file for keys) - for example:

```
 <img src={props.image} alt={props.name} />
```

### 2. in App.js use .map() method to render all foods from json

-> (no state neccessary here)

```
   {foodsList.map((food) => {
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

## Iteration 3 - Add new food form

### 1. create new AddFoodForm.js component

### 2. create onSubmit-Form with all input values (name, image, calories, servings)

```
   <div class="AddFoodForm">
      <div className={isHide ? 'show' : 'hide'}>
        <form onSubmit={submitButton}>
          <label>Name</label>
          <input
            name="name"
            value={addedFood.name}
            type="text"
            onChange={handleInputChange}
          />
          <label>Image</label>
          <input
            name="image"
            value={addedFood.image}
            type="text"
            placeholder="https://via.placeholder.com/30x30"
            onChange={handleInputChange}
          />
          <label>Calories</label>
          <input
            name="calories"
            value={addedFood.calories}
            type="number"
            onChange={handleInputChange}
          />

          <button type="submit" id="buttonCreate">
            Create
          </button>
        </form>
      </div>
```

### 3. create useState for addedFood with initial states for these values (empty strings)

```
   const [addedFood, setAddedFood] = useState({
   name: '',
   image: '',
   calories: '',
   servings: '',
   });
```

### 4. create function to handleInputChange (important call setAddedFood)

--> all fields with onChange

```
   const handleInputChange = (event) => {
   const value = event.target.value;
   setAddedFood({ ...addedFood, [event.target.name]: value });
   };
```

### 5. create function for submitButton and define function handleSubmit as props to App.js

```
const submitButton = (event) => {
props.handleSubmit(event, addedFood);
};
```

## // function to hide

### 6. add useState to change isHide state

-> set initial state to 'false'

```
const [isHide, setIsHide] = useState(false);
```

### 7. create function to hide/show form in button

-> setIsHide function will always do what is different the current state (!isHide)

```
  const handleHide = () => {
    setIsHide(!isHide);
  };
```

## 8. add property in App.css with class with default not displayed

```
.hide {
  display: none;
}
```

## 9. add div around Form with className

-> use iternary to change className

```
<div className={isHide ? 'show' : 'hide'}>
```

## // Lift up to App.js

### 10. import AddFoodForm.js to App.js

```
import AddFoodForm from './components/AddFoodForm';
```

## 11. add useState to change rendered FoodsList

```
const [foods, setFoods] = useState(foodsList);
```

## 12. add function handleSubmit (for props from AddFoodForm)

```
    const handleSubmit = (event, newFood) => {
    event.preventDefault();
    const updateFood = [newFood, ...foods];
    setFoods(updateFood);
    };
```

## 13. add AddFoodForm.js component in return to render

```
    <AddFoodForm handleSubmit={handleSubmit} />
```

## 14. change the array that uses .map()

-> now we not tell to render foodsList from json only, but also the added food
-> so use foods from state

```
foods.map()
...
```

---

# Iteration 4 - Search

## 1. add state for filteredFoods

```
const [filteredFoods, setFilteredFoods] = useState('');
```

## 2. add function handleSearchInput

```
const handleSearchInput = (event) => {
setFilteredFoods(event.target.value);
};
```

## 3. add searchbar html

-> add input field in return of App.js (no need to create extra component)

```
<div className="Searchbar">
         <input
            value={filteredFoods}
            placeholder="Search food"
            type="text"
            onChange={handleSearchInput}
          />
        </div>
```

## 4. change your foods.map()

-> filter before map + iternary operator for when foodsList = 0)
-> when filter make it case-insensitive with toLocaleLowerCase()

```
{foods.length === 0 ? (
            <h1>Oops! There is no more content to show</h1>
          ) : (
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
          )}
```

## Iteration 5 - Create add-button // Todays Food

### 1. Create new State

-> state with empty array

```
const [todaysFoods, setTodaysFoods] = useState([]);
```

### 2. Create handleAddFood function in App.js

-> function to add value to todaysFood, when clicking on add-button

```
 const handleAddFood = (addedFood) => {
    setTodaysFoods((prevTodaysFood) => [addedFood, ...prevTodaysFood]);
  };
```

### 3. Pass down handleAddFood into child component FoodBox.js

```
<FoodBox food={food} onAddFood={handleAddFood} />
```

### 4. Inside FoodBox.js

--> add onClick event on button(+); through onClick we sending the updated food object with new amount from input field

```
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

```
 const [amount, setAmount] = useState(1);
```

--> create function to handle amount input field

```
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

```
  const [isHide, setIsHide] = useState(false);
```

-> Wrap a div around whole form:

```
<div className={isHide ? 'show' : 'hide'}>
...
</div>
```

-> write function to handle this state:

```
  const handleHide = () => {
   setIsHide(!isHide);
 };
```

-> add these html in your return:

```
  <button id={isHide ? 'hide' : 'show'} onClick={handleHide}>
      {isHide ? 'Hide' : 'Show'}
    </button>
```

-> at least define a class in your CSS

```
.hide {
display: none;
}
```