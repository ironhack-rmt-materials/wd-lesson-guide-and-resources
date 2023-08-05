

# JS - Functions Intro


<!--- 

Status: ready

Time: 1h

-->


## Intro 

- warmup (why functions are useful): https://stackblitz.com/edit/js-nd3zvj?file=index.js
  
  <!-- @Luis: fork -->
  <!-- @todo: improve example (do any operation that requires multiple lines (ex. any code from yesterday's lab)) -->


  - solve with 2 console.log (repeating code)
  - task: "Create a function that receives the age of 3 students + displays the average age"

  - Final result: https://stackblitz.com/edit/js-lzhtaj?file=index.js



## Functions Basics


- Why functions are useful (reuse code)

- How to create a function (syntax)
  
  ```js
  function sayHello(){
    console.log("hello world")
  }
  ```

- Call / Invoke

- Naming functions
  - camelCase
  - descriptive
  - Verb


## Arguments

- Create multiple functions: `sayHelloAlice`, `sayHelloBob`

- Use arguments instead
  - Why arguments: reusable code
  
- Multiple arguments: `username`, `favouriteDrink`
  - Note: order is important


- (skip) Parameter vs. Argument
- Parameters = placeholder
- Argument = the values (passed to function in the moment of its invocation)
- (Mnemonic: arguments come from outside).
- The number of parameters & arguments could be different (ex. expecting 3, passing only 2 arguments)


- (skip) Default parameters
  - allow parameters to be initialized with default values if no value or undefined is passed.


(short break)


## Return

<!-- Note: do example with calcMult -->

```js
function calcMult(a, b){
  const result = a * b;
  // console.log(result);
  return result;
}
```

- IMPORTANT: returns vs. console.log
- IMPORTANT: a function without a return, returns `undefined`

- Multiple returns
- IMPORTANT: return finishes execution of the function

- Return multiple values:
- Q: what can we do if we need return multiple values ??
  (ex. get name of 2 users.)
- Solution: data structure (array, object)



## Practice: JS Functions

  - Iteration 1:
    - Create a function `calcTotal()` that accepts 3 numbers as parameters, and returns their sum.

  - Iteration 2:
    - Create a function named `isNameOddOrEven()` that accepts a string as a parameter. 
    - The function should return whether a received string has an odd or even number of letters (hint: str.length).
    - The expected return should be in the following format - string: `<name> has an <even/odd> number of letters`

  - Bonus: 
    - research/practice "JS default parameters" (https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters)


  - Time: 15min/20min.


  - Solution: https://stackblitz.com/edit/js-ew4qjq?file=index.js






## Writing good functions (Good practices)
  - Reuse code
  - (Abstraction) (skip)
  - (Separation of Concerns) (skip)
  - Single Responsibility Principle


## Refactoring

  > Code Refactoring is a technique in software development by which we change the way the code is structured, keeping the same functionality.


