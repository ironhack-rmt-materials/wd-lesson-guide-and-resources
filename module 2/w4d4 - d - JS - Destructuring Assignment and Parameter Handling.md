# JS - Destructuring Assignment and Parameter Handling

<!--- 

- Status: in progress (only missing the sections marked with @todo)

- Also highlighted (WDFT+202107_RMT)

- Note: 
  - focus on the most common use cases (basic object and array destructuring)
  - alternative variable names, default values, etc -> just mention them
  - GOAL: go through this lesson quick so that we have more time for PROMISES, LABS,....

- FUNDAMENTALS:
  - Object destructuring
  - Array destructuring (briefly)
  - Spread operator
  
- IMPORTANT:
  - Spread Operator: if we still didn't have time to speak about copying by value vs. reference., this is the perfect moment (when we speak about spread operator to copy an array)
  - Value vs. Ref. & copies: https://stackblitz.com/edit/js-rfdnid?file=index.js


-->



## Intro

- So far we've learn how to read data from arrays and objects

- Arrays: we can access individual elements in an array by their position (index)
  -- students[0]

- Objects: we can access elements using `dot notation` or `bracket notation`
  -- student.name
  -- student['name']

- In this lesson, we will learn an easy and convenient way of extracting data from arrays and objects: `Destructuring`
  -- Destructuring == breaking down complex data structures into simpler ones that are easier to use.


## Object destructuring

- Example of how to access properties using dot/bracket notation. Eg:

    ```
    let person = {
        name: 'Ironhacker',
        age: 25,
        favoriteMusic: 'Rock',
    };

    let name = person.name;
    let age = person.age;
    let favoriteMusic = person.favoriteMusic;

    console.log(`Hello, ${name}.`);
    console.log(`You are ${age} years old.`);
    console.log(`Your favorite music is ${favoriteMusic}.`);

    ```

Problem: it works but, if we have to access many properties it is a bit repetitive.


- With object destructuring:
    ```
    let { name, age, favoriteMusic } = person;
    ```

- Note: we're creating variables with the same names as the properties of our object.

- Compare:

    ```
    // ES5 way:
    const name = person.name;
    const age = person.age;
    const favoriteMusic = person.favoriteMusic;

    // ES6 way (using destructuring)
    const { name, age, favoriteMusic } = person;

    ```


- Default values

    ```
    let { name, age, favoriteMusic, country = 'Spain' } = person;
    ```

- Different variable names


    ```
    const { name: fullName, age, favoriteMusic } = person;
    ```



## (skip) Nested objects and destructuring

- We can also apply destructuring for nested objects.

Example:

    ```
    const person = {
    name: 'Ironhacker',
    age: 25,
    favoriteMusic: 'Metal',
    address: {
        street: 'Super Cool St',
        number: 123,
        city: 'Miami',
    },
    };


    let {
      name,  age, favoriteMusic,
      address: { street, number, city },
    } = person;

    ```


## Exercise: practice object destructuring

https://stackblitz.com/edit/js-eu43id

Time: 10+5m







## Array destructuring

- Very similar to object destructuring, we give names to the variables inside brackets.

- Example:

    ```
    const campuses = ['madrid', 'barcelona', 'miami'];

    const [firstCampus, secondCampus, thirdCampus] = campuses;
    ```

  - NOTE: ORDER MATTERS! (in object destructuring order is not important)



- Skipping elements:
    ```
    const [ , , thirdCampus] = campuses;
    ```


- Default values

  - If there are not enough elements in the array, we'd get `undefined`
  - It is also possible to set a default value.

    ```
    const [campus1, campus2, campus3, campus4 = 'paris'] = campuses;
    console.log(campus4); // ==> paris
    ```



## (skip) Nested arrays and destructuring


    ```
    const europeanCampuses = [
      ['madrid', 'es'],
      ['barcelona', 'es'],
      ['berlin', 'de'],
      ['paris', 'fr'],
      ['amsterdam', 'nl'],
      ['lisbon', 'pt']
    ];

    const [
      [campusOneCity, campusOneLang],
      [campusTwoCity, campusTwoLang]
    ] = europeanCampuses;

    console.log(campusOneCity, campusOneLang);
    console.log(campusTwoCity, campusTwoLang);

    ```


## Exercise: practice array destructuring

- (optional) Exercise:
https://stackblitz.com/edit/js-7uq7wm



Note:
- We will use Object destructuring a lot.
- Array destructuring is less common






## Spread operator

@todo

- The spread operator:
  - lets us "unpack" elements of an array to single/individual arguments.
  - can be used when all elements from an object or array need to be included in a list of some kind.



Examples using the spread operator:

- Adding elements to array
  ```
  const newArr = [...students, "david"]
  ```

- Merging arrays

  ```
  const newArr = [...arrOne, ...arrTwo]
  ```

- Copying arrays
  
  ```
  const copy = [...students]
  ```




## (skip) Rest parameter

@todo


```
  function add(...numbers) {
    // numbers represents the arguments passed when function gets invoked
    let sum = 0;
    for (let oneNumber of numbers) {
      sum += oneNumber;
    }
    return sum;
  }
  
  add(1); // 1
  add(1, 2); // 3
  add(1, 2, 5, 8); // 16
```


- Exercise (practice rest parameters + arr.reduce): 
https://stackblitz.com/edit/js-o9cpuo



## Practice

@todo

exercise to practice:
- object destructuring
- spread operator





## Exercise: Mixed destructuring (Optional -- Only if plenty of time)

Skip (not relevant)



## (Extra) Destructuring function parameters

- It is also possible to apply destructuring when we receive arguments in a function declaration.

Example:

```
function printFullName(actor) {
  console.log(`${actor.firstName} ${actor.lastName}`);
}

const actor = { firstName: 'Brad', lastName: 'Pitt' };

printFullName(actor);

```


We can also do the following:

```
function printFullName({ firstName, lastName }) {
  console.log(`${firstName} ${lastName}`);
}
```






