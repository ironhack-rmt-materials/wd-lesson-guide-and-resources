

# JS - Functions Intro


<!--- 

Status: ready

Time: 1.5

-->


## Intro 

- warmup (why functions are useful): https://stackblitz.com/edit/js-xe5ej8?file=index.js
  <!-- @Luis: fork -->
  - solve with 2 console.log (repeating code)
  - task: "Create a function that receives the age of 3 students + displays the average age"



## Topics / Concepts 


- Why functions are useful (reuse code)

- How to create a function (syntax)
  
  ```
  function sayHello(){
    console.log("hello world")
  }
  ```

- Call / Invoke

- Naming functions
  - camelCase
  - descriptive
  - Verb

- Arguments
  - Create multiple functions: `sayHelloAlice`, `sayHelloBob`
  - Use arguments instead
    - Why arguments: reusable code
  - Multiple arguments: `username`, `favouriteDrink`
    - Note: order is important

- (skip) Parameter vs. Argument
  - Parameters = placeholder
  - Argument = the values (passed to function in the moment of its invocation)
  - The number of parameters & arguments could be different (ex. expecting 3, passing only 2 arguments)


- (bonus) Default parameters
  - allow parameters to be initialized with default values if no value or undefined is passed.


- Return
  - create a function `getMessage` & store the result in a variable
    - alternative: `calcTotal`
  - IMPORTANT: returns vs. console.log
  - IMPORTANT: a function without a return, returns `undefined`

- Multiple returns
  - IMPORTANT: return finishes execution of the function

- Return multiple values:
  - Q: what can we do if we need return multiple values ??
    (ex. get name of 2 users.)
  - Solution: data structure (array, object)



- Quick Exercise (5-15min.):

  - Iteration 1:
    - Create a function `calcTotal()` that accepts 3 numbers as parameters, and returns their sum.

  - Iteration 2:
    - Create a function named `isNameOddOrEven()` that accepts a string as a parameter. 
    - The function should return whether a received string has an odd or even number of letters. 
    - The expected return should be in the following format - string: `<name> has an even/odd number of letters`


  - Solution: https://stackblitz.com/edit/js-ew4qjq?file=index.js



- Writing good functions (Good practices)
  - Reuse code
  - (Abstraction) (skip)
  - (Separation of Concerns) (skip)
  - Single Responsibility Principle


- Refactoring

  > Code Refactoring is a technique in software development by which we change the way the code is structured, keeping the same functionality.


