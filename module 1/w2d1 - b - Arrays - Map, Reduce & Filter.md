# Arrays - Map, Reduce & Filter

<!-- 
Status: draft
-->


## Important:

.map(), .filter() and .reduce():
  - these methods DON’T modify the original (they don’t mutate the original array but rather create a new array)

- Visual cheatsheet with some array methods:
  https://res.cloudinary.com/practicaldev/image/fetch/s--sYEjzdnw--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/sr8koff729gxcvpnoty6.jpeg



## Map:


- Intro exercise (before explaining map): 

  - Any basket fan? Michael Jordan last shot with the Bulls: 
    - https://pbs.twimg.com/media/EYWEL13XkAcHnxm?format=jpg&name=4096x4096


  ```javascript
  const baskets = [11, 14, 7, 12, 9, 12]; // 2 point baskets in his last games with the bulls
  ```

  Task: 
  - create an array with the points from regular baskets for each game.
  - note: each basket is 2 points, so we need to multiply by 2.
  - expected result:
    - `const points = [22, 28, 14, 24, 18, 24];`


  Options:
  - Solve with for loop
  - Solve with forEach
    - Bonus: solve using different type of functions (anonymous, arrow...)

  Solution: https://stackblitz.com/edit/js-k66y7n?file=index.js

  Time: 10min.





- Explain map() method.
  
  - .map() is usuful whenever we need to apply a transformation to all elements in an array.
  
  - diagram: https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_c465728a5460c8d562936d4f1b5d18cc.png 

  - notice: the number of elements in the new array is the same.

  - see documentation (MDN)
    - very similar to .forEach()


- Solve using .map()
  - NOTE: .map() returns a new array but DOES NOT modify the original 



- Example 2: transform names to uppercase
  - Instructions: https://stackblitz.com/edit/js-dm5iu3?file=index.js
  - solution with for loop: https://stackblitz.com/edit/js-reuufm?file=index.js
  - solution with forEach: https://stackblitz.com/edit/js-ypkht5?file=index.js
  - solution with map: https://stackblitz.com/edit/js-i296ku?file=index.js



- Example 3: with objects.

  - Instructions: https://stackblitz.com/edit/js-p3k5so?file=index.js
  - Solution: https://stackblitz.com/edit/js-ejcare?file=index.js

  Time: 10min.


- Example 4: with objects.

  ```javascript
    const students = [
      {
        name: 'alice',
        city: 'paris',
      },
      {
        name: 'bob',
        city: 'tokio',
      },
      {
        name: 'charly',
        city: 'berlin',
      },
    ];
  ```

  
  - TASK:

  1. Create an array with the names of all students. Example: ["alice", "bob", "charly"]
  2. (Bonus) Same as above but with all names in uppercase. Example: ["ALICE", "BOB", "CHARLY"]

  - solution: https://stackblitz.com/edit/js-9urdsg?file=index.js


  Note: they will need something similar in today's LAB (iteration 1)



---
---


Even more exercises with .map()



- Students portal I: 
  > Given an array of cities, return an array with the first letter of each city’s name capitalized...

- Students portal II: 
  > Imagine you are a Math teacher ...


- Exercise 3: Sales + average


- Exercise 4 (with objects): 


- Bonus: solve it with different kind of functions
  - with an anonymous function
  - with an anonymous arrow function
  - with function that has been declared previously


---
---



## Reduce:


<!--
- DEMO EXPLANATION .reduce() with numbers:

// const baskets = [4, 6, 7, 0, 10];

https://stackblitz.com/edit/ih-reduce-method-explained?file=index.js


-->


- Intro (helps understand reduce better):


```javascript
  const baskets = [4, 6, 7, 0, 10];

  // Task:
  // Calculate the total amount of baskets


  // Option 1: with a forEach()
  let total = 0;
  baskets.forEach((element) => {
    // total = total + element;
    total += element;
  });

```


- Signature:

  ```js
    reduce(function(accumulator, currentValue) { /* ... */ }, initialValue)
  ```



- Example: 

  ```js
  array.reduce(function (accumulator, currentValue) {
      return accumulator + currentValue;
  });
  ```

  - accumulator is an accumulated value of each call
    - (IMPORTANT) In the first round, it’s assumed it’s the first value from the array unless we state differently (which we will see how).

  - currentValue is the current element in each iteration that will be added to the accumulator.



- Setting an initial value:

  ```js
      arr.reduce( function(acc, curr){ ... }, initialValue)
  ```




- (optional) Example: with strings

  <!-- @Luis: optional / quick extra example -->

  ```js
  const words = ["the", "quick", "brown", "fox"];


  const sentence = words.reduce(function(acc, currentValue){
    return acc + " " + currentValue;
  }, "")

  console.log(sentence);
  ```



- Example: with objects

  - Instructions: https://stackblitz.com/edit/js-aervwj?file=index.js
  - Solution: https://stackblitz.com/edit/js-xufcpn?file=index.js
    - IMPORTANT: in this case we need to set an inital value.



- CFU (same as students portal)


  ```javascript
  const menu = [
    { name: 'Carrots', calories: 150 },
    { name: 'Steak', calories: 350 },
    { name: 'Broccoli', calories: 120 },
    { name: 'Chicken', calories: 250 },
    { name: 'Pizza', calories: 520 },
  ];

  //console.log(averageCalories); // should display 278
  ```

  TASK:
  - Calculate the average number of calories.

  Time: 10min.

  Solution: https://stackblitz.com/edit/ih-reduce-method-explained-q3quwc?file=index.js


  <!--

  TODAY'S LAB: 
  
  They'll need to pass extra tests:
  - ex. what happens if a recipe does not have the property `calories`
  - ex. returning the average in a specific format (rounded to 2 decimals)
  
  -->




## Filter:

-  iterates through an array and creates a new array with all elements that pass the condition we set


- Example 1:

  ```javascript
  const cities = [
    'miami',
    'barcelona',
    'madrid',
    'amsterdam',
    'berlin',
    'sao paulo',
    'lisbon',
    'mexico city',
    'paris'
  ];
  ```

  TASK:
  - get only the cities with 6 letters
  - (bonus) get only the cities that contain letter 's'




- Example 2: with an array of objects


  ```javascript

    const people = [
      { name: 'alice', age: 30 },
      { name: 'bob', age: 18 },
      { name: 'charly', age: 49 },
      { name: 'david', age: 21 },
      { name: 'emma', age: 17 }
    ];

  ```

  TASK: 
  - get an array with all people above 20.

  Solution: https://stackblitz.com/edit/js-bdtvhz?file=index.js





## (IMPORTANT) Identify & combine:
  - identifying which method we can use can be tricky. Solution: practice.
  - we can combine multiple methods. 
    - Ex: `.filter().reduce()`
    - Ex: `.filter().map()`





## Extra:

- Cheatsheet
  - just google images "js array methods"

  - Cheatsheet Meme (map vs filter vs reduce): 
    https://res.cloudinary.com/practicaldev/image/fetch/s--fR01rwJz--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/3158n4nhe7gt24wvl2u4.png

- Mutating vs. non-mutating methods:
  https://miro.medium.com/max/1400/1*hav8uvwoznX0JITWDOCvFw.png


- Cheatsheet (gist) with array methods (includes sort):
  - https://gist.github.com/TA-Remote/505bb6969851737d76603143a6b45c55







