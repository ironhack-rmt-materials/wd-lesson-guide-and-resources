# JS - Destructuring Assignment


<!--- 

- Status: ready

- Notes: 
  - focus on the most common use cases (basic object destructuring)
  - alternative variable names, default values, etc: just mention it
 
-->



## Object destructuring


- Example:

    ```js
    const user = {
        company: 'Ironhacker',
        age: 30,
        favoriteMusic: 'Rock',
    };

    const company = user.company;
    const age = user.age;
    const favoriteMusic = user.favoriteMusic;

    // note: we can also use square bracket notation
    // const company = user["company"];

    console.log(`You work at ${company}`);
    console.log(`You are ${age} years old`);
    console.log(`Your favorite music is ${favoriteMusic}`);

    ```

Problem: it works but, if we have to access many properties it is a bit repetitive.


- With object destructuring:
    ```js
    const { company, age, favoriteMusic } = user;
    ```

- Note: we're creating variables with the same names as the properties of our object.

- Compare:

    ```js
    // ES5 way:
    const company = user.company;
    const age = user.age;
    const favoriteMusic = user.favoriteMusic;

    // ES6 way (using destructuring)
    const { company, age, favoriteMusic } = user;

    ```


- Default values

    ```js
    let { company, age, favoriteMusic, country = 'Spain' } = user;
    ```

- Different variable names


    ```js
    const { company: employer, age, favoriteMusic } = user;
    ```


- (skip) Nested objects and destructuring



## Practice: object destructuring

- Instructions: https://stackblitz.com/edit/js-eu43id
- Time: 10min.

- Solution: https://stackblitz.com/edit/js-eigzjc?file=index.js





## (brief) Array destructuring

- Very similar to object destructuring, we give names to the variables inside brackets.

- Example:

    ```js
    const campuses = ['madrid', 'barcelona', 'miami'];

    const [firstCampus, secondCampus, thirdCampus] = campuses;
    ```

  - NOTE: ORDER MATTERS! (in object destructuring order is not important)



- Skipping elements:
    ```js
    const [ , , thirdCampus] = campuses;
    ```


- (skip) Default values

  - If there are not enough elements in the array, we'd get `undefined`
  - It is also possible to set a default value.

    ```js
    const [campus1, campus2, campus3, campus4 = 'paris'] = campuses;
    console.log(campus4); // ==> paris
    ```

- (skip) Nested arrays and destructuring

- (skip) Exercise: practice array destructuring
  - https://stackblitz.com/edit/js-7uq7wm




## (brief) Destructuring function parameters

- It is also possible to apply destructuring when we receive arguments in a function declaration.

Example:

  ```js


  function printFullName(actor) {
    console.log(`${actor.firstName} ${actor.lastName}`);
  }

  const actor = { 
    firstName: 'Brad', 
    lastName: 'Pitt' 
  };

  printFullName(actor);

  ```


We can also do the following:

  ```js
  function printFullName({ firstName, lastName }) {
    console.log(`${firstName} ${lastName}`);
  }
  ```





## Final notes:
- We will use Object destructuring a lot.
- Array destructuring is less common


