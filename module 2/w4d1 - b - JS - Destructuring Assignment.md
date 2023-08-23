# JS - Destructuring Assignment

<!--- 

- Status: ready

- Notes: 
  - focus on the most common use cases (basic object destructuring)
  - alternative variable names, default values, etc: just mention it
 
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


```js
const users = ["alice", "bob", "charly"];

let user = {
    company: 'Ironhacker',
    age: 30,
    favoriteMusic: 'Rock',
};

```



## Object destructuring

- Example of how to access properties using dot/bracket notation. Eg:

    ```js
    let user = {
        company: 'Ironhacker',
        age: 30,
        favoriteMusic: 'Rock',
    };

    let company = user.company;
    let age = user.age;
    let favoriteMusic = user.favoriteMusic;

    console.log(`You work at ${company}.`);
    console.log(`You are ${age} years old.`);
    console.log(`Your favorite music is ${favoriteMusic}.`);

    ```

Problem: it works but, if we have to access many properties it is a bit repetitive.


- With object destructuring:
    ```js
    let { company, age, favoriteMusic } = user;
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




## (skip) Nested objects and destructuring

- We can also apply destructuring for nested objects.

Example:

    ```js
    const user = {
      company: 'Ironhacker',
      age: 25,
      favoriteMusic: 'Metal',
      address: {
          street: 'Super Cool St',
          number: 123,
          city: 'Miami',
        },
    };


    let {
      company,  age, favoriteMusic,
      address: { street, number, city },
    } = user;

    ```



## Practice: object destructuring

Practice: Object Destructuring
- Instructions: https://stackblitz.com/edit/js-eu43id
- Time: 10min.

- Solution: https://stackblitz.com/edit/js-eigzjc?file=index.js





## (skip) Array destructuring

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


- Default values

  - If there are not enough elements in the array, we'd get `undefined`
  - It is also possible to set a default value.

    ```js
    const [campus1, campus2, campus3, campus4 = 'paris'] = campuses;
    console.log(campus4); // ==> paris
    ```



## (skip) Nested arrays and destructuring


    ```js
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


## (skip) Exercise: practice array destructuring

- (optional) Exercise:
https://stackblitz.com/edit/js-7uq7wm




Notes:
- We will use Object destructuring a lot.
- Array destructuring is less common


