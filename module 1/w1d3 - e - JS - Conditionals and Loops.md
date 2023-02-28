# JS - Conditionals and Loops



Methodology:
- we probably don't need to go in detail for the theory
- instead, ask them to solve "FizzBuzz" + solve it together


FizzBuzz:
  - how: small teams (2-3 people)
  - time: 20-25m + solve together
  - https://stackblitz.com/edit/js-fizbuzz-exercise-p4hr4j?file=index.js



## Notes


- if…else
- switch
- do…while
- for
- for…of
- break
- while



## for...of

```js
const someIterable = 'amsterdam';
 
for (const value of someIterable) {
  console.log(value);
}
```



## EXTRA: Ternary operator

- Syntax:

  `condition ? exprIfTrue : exprIfFalse`


- Example 1: initial code with if-else 

  ```js
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

  ```js
  const name = 'alice';
  const likesPizza = name === 'alice' ? true : false;

  console.log(likesPizza);
  ```



  


- Example 2, returning from a function:
  
  ```js
  function getUserRole() {
    
    let name = "alice";

    if (name === "alice") {
      return 'admin';
    } else {
      return 'standard';
    }
  }

  const role = getUserRole();
  console.log(role);

  ```

- Example 2, with ternary operator:

  ```js
  function getUserRole() {
    let name = "alice";

    return (name === "alice") ? 'admin' : 'standard';
  }

  const role = getUserRole();
  console.log(role);
  ```
