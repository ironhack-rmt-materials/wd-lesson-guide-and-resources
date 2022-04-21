# Arrays - Map, Reduce & Filter

<!-- 
Status: draft
-->

## Important:

.map(), .filter() and .reduce()  DON’T modify the original 
--> they don’t mutate the original array but rather create a new array

- Visual cheatsheet with some array methods:
  https://res.cloudinary.com/practicaldev/image/fetch/s--sYEjzdnw--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/sr8koff729gxcvpnoty6.jpeg


## Map:

- Intro exercise (before explaining map): 
  - https://stackblitz.com/edit/js-dm5iu3?file=index.js
  - solution with for loop: https://stackblitz.com/edit/js-reuufm?file=index.js
  - solution with forEach: https://stackblitz.com/edit/js-ypkht5?file=index.js



- Explain map() method.



- Exercise 1: 
  - Given an array of cities, return an array with the first letter of each city’s name capitalized ...

- Exercise 2: 
  - https://stackblitz.com/edit/js-3brxxe?file=index.js
  - solution: https://stackblitz.com/edit/js-nf7aaz?file=index.js

- Exercise 3 (with objects): 
  - note: they will need something similar in today's LAB
  - https://stackblitz.com/edit/js-dzh9td?file=index.js
  - solution: https://stackblitz.com/edit/js-zvxlcc?file=index.js



## Reduce:

<!--
- DEMO EXPLANATION reduce() method with numbers:

https://stackblitz.com/edit/ih-reduce-method-explained?file=index.js


-->


- Intro (helps understand reduce better):

```
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


- Example: 

```
array.reduce(function (accumulator, currentValue) {
    return accumulator + currentValue;
});
```

- accumulator is an accumulated value of each call
  - IMPORTANT: In the first round, it’s assumed it’s the first value from the array unless we state differently (which we will see how).

- currentValue is the current element in each iteration that will be added to the accumulator.


- Setting an initial value:

```
    arr.reduce( function(acc, curr){ ... }, initialValue)
```

- Sometimes it can get tricky. 
  - Example: with objects (in this case we need to set an inital value):

```
    const people = [
    { name: 'Candice', age: 25 },
    { name: 'Tammy', age: 30 },
    { name: 'Allen', age: 49 },
    { name: 'Nettie', age: 21 },
    { name: 'Stuart', age: 17 }
    ];

    const ages = people.reduce(function (sum, person) {
    return sum + person.age;
    }, 0); // initialValue to 0

    console.log(ages); // <== 142

```



## Filter:

-  iterates through an array and creates a new array with all elements that pass the condition we set


- Exercise:
```
// get only the cities with 6 letters
// get only the cities that contain letter 's'

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


## Extra:

- Cheatsheet Meme: 
https://res.cloudinary.com/practicaldev/image/fetch/s--fR01rwJz--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/3158n4nhe7gt24wvl2u4.png





