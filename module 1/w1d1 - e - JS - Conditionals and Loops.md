# JS - Conditionals and Loops

Methodology:
- we probably don't need to go in detail for the theory
- instead, ask them to solve "FizzBuzz" + solve it together


FizzBuzz:
  - how: small teams (2-3 people)
  - time: 20-25m + solve together
  - https://stackblitz.com/edit/js-fizbuzz-exercise-p4hr4j?file=index.js



## EXTRA: Ternary operator

- Syntax:

  `condition ? exprIfTrue : exprIfFalse`


- Example 1: initial code with if-else 

  ```javascript
  const name = 'alice';
  let likesPizza;

  if (name === 'alice') {
    likesPizza = true;
  } else {
    likesPizza = false;
  }

  console.log(likesPizza);
  ```

- Example 1 with ternary operator:

  ```javascript
  const name = 'alice';
  const likesPizza = name === 'alice' ? true : false;

  console.log(likesPizza);
  ```


- Example 2, returning from a function:
  
  ```javascript
  function getUserRole() {
    const isGod = true;

    if (isGod) {
      return 'admin';
    } else {
      return 'standard';
    }
  }

  const role = getUserRole();
  console.log(role);

  ```

- Example 2, with ternary operator:

  ```javascript
  function getUserRole() {
    const isGod = true;
    return isGod ? 'admin' : 'standard';
  }

  const role = getUserRole();
  console.log(role);
  ```
