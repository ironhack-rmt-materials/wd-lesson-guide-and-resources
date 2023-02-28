

# Functions Advanced


<!--- 
    Status: complete
--->


## Intro


- We've already seen how we can declare & use functions

    ```js
    function calcSum() {
        console.log("hello")
    }

    
    calcSum();
    ```

- This is called a function declaration (aka statement)
- pass arguments
- return

- JavaScript is a programming language with `first-class functions` (functions are treated like any other variable)
  - a function can be assigned as a value to a variable
  - a function can be passed as an argument to other functions
  - a function can be returned by another function 

> example "a function can be passed to other functions": `forEach()`



## Function Expressions

- We know that we can store a function in a variable

- Example (calc Multiplication):

    ```js
    const calcMult = function(x, y) {
        return x + y;
    };

    calcMult(2, 3);
    ```

- Compare both syntaxes
  - notice, it's a function 'without the name'.

  - a function expression is an un-named function (aka **Anonymous Function**) that is stored in the variable.



## Function declaration vs. function expression

- The syntax we use to create them is different but:
  - to call (invoke) the function, the syntax is the same
    - `doSomething()`

  - both can be reused throughout the code.

- Main difference:
  - function expression: we can not call the function before it has been created
    - makes sense: show example of the same with variables
  - function declaration: a function call can be 'before' the function declaration
    - why? Hoisting (lesson next week)


- Should I use function declarations of function expression?
  - Consistency
    - Whichever you decide to use, stick with it
    - When you join a dev team, if there's a convention, stick to it



--- 
(break)

--- 


## Timeouts & intervals

- Why?
  - Sometimes we want to perform an action after a specific time.
    - Example: display a confirmation message + hide it after 10 seconds.


- Timeout

  ```javascript
    setTimeout(function () {
      console.log('done!');
    }, 1000);
  ```


- Interval


- Clearing timeout / interval
  - clearTimeout()
  - clearInterval()




Practice: timers and intervals
  1. Create an interval that displays a counter every second
    - in the console, display: "hello 1", "hello 2", "hello 3".....
  2. After 5 seconds, cancel that interval
  3. (Bonus) Apply what we've learned so far and Try to solve it in different ways.

  How: individual
  Time: 15min.

  Solution 1 (with a timeout): 
  - https://stackblitz.com/edit/js-vhkxbm?file=index.js
  Solution 2 (checking the counter): 
  - https://stackblitz.com/edit/js-sjpn4f?file=index.js


Note: most students find it difficult, give them 15min. and solve together.



## Callbacks

<!--
@Luis: 
- explain the concept of a callback
- leave the examples for w2d2 (unit "Async and callbacks")
-->

- Callback = when we pass a function as an argument to another function
  - example: `forEach()`
  - example: `setTimeout()`


- How else can be useful?

Initial example:

    ```javascript
        function cookDinner() {
            console.log('Preparing dinner...');
            console.log('Dinner is ready');
        }

        function eatDinner() {
            console.log('Eating dinner');
        }

        cookDinner();
        eatDinner();
    ```



But... dinner takes time to be prepared....


    ```javascript
    function cookDinner() {
        console.log('Preparing dinner...');
        setTimeout(function() {
            console.log('Dinner is ready');
        }, 1000);
    }

    function eatDinner() {
    console.log('Eating dinner');
    }

    cookDinner();
    eatDinner();

    ```



So we can pass it a function to be executed at the end (once dinner is ready)...

  ```javascript
  function cookDinner(myCallback) {
    console.log('Preparing dinner...');
    setTimeout(function() {
        console.log('Dinner is ready');
        myCallback();
    }, 1000);
  }

  function eatDinner() {
    console.log('Eating dinner');
  }

  cookDinner(eatDinner); //notice: we don't have ()

  ```


- Usually, when we pass one function as an argument we refer to it as a `'callback'` 


- IMPORTANT: 
  - when you're passing a function as a callback, make sure not to use ()


- When and why any function would be postponed/delayed in the real world?
  - Interact with the UI
  - Wait for some data from a database
  - Wait for some data that we get from a different server
  - ...



- Practice: JS Callbacks

  - Instructions: https://stackblitz.com/edit/js-graftg?file=index.js
  - Time: 15min.

  - Solution: https://stackblitz.com/edit/js-dzfqat?file=index.js



## Anonymous functions

- An anonymous function is a function without a name.

- Why ?
  - if it will be used just in that very moment and never again in your code

- Example:
  - call setTimeout
    - pass a function created with a function declaration / function expression
    - pass an anonymous function




## Arrow Functions

- Alternative syntax to create an anonymous function
- (they're a different way to create functions)
- Introduced with ES6

- Example:

  ```js
  // function expression syntax
  const sayHello = function(userName) {
    console.log(`Hello, ${userName}!`);
  };

  // arrow function syntax
  const sayGoodbye = (name) => {
    console.log(`Goodbye, ${name}!`);
  };

  ```


- Syntax:
  - when we can ommit parenthesys (only one arg)
    - `one paramenter -> we can remove the parenthesys`
  - when we can ommit curly braces (only one line)
    - `if the function directly returns an expression -> curly braces can only be omitted & the return will be implicit.`


- "Traditional" vs "Arrow" functions
  - quite much the same
  - which one to use: 
    - consistency
    - in some cases we'll need to use one or the other (ex. this)

- Arrow functions don't have their own bindings to `this`.

  - > Arrow functions don't have their own bindings to this, arguments, or super, and should not be used as methods.

  - "Arrow function expressions should only be used for non-method functions because they do not have their own `this`"

- Arrow functions... "this" is the difference:
![this is the difference](./images/arrow-functions-this-is-the-difference.jpg)



## Practice: different ways of creating functions (+ delays & callbacks) 


<!--

Notes:
- iteration 1 is great to practice (10min)
- iteration 3 can be challenging for many students (10% completed after 20min)

We will practice:
- different ways to create functions
  - function declaration
  - function expression
  - arrow function
- anonymous functions
- delays & callbacks

-->

- Instructions: https://stackblitz.com/edit/js-aqnh5t?file=index.js
- Time: 15-20min.

- Solution: https://stackblitz.com/edit/js-dmxv6n?file=index.js






## (skip) The arguments object

<!-- skip this part (arguments object) -->

- Inside the body of a function, you can access an object called `arguments`.
- This object contains the values of the arguments passed to that function.


Example:
```
    function printSomething() {
        console.log(arguments);
    }

    printSomething('hi');

    // [Arguments] { '0': 'hello' }

```

- It is a special kind of object called `array-like object`

  > “Array-like” means that arguments has a length property and properties indexed from zero, but it doesn't have Array's built-in methods like forEach() or map()

- Accessing it's values is a bit different.

  - One option is to convert it to an array. For example:

    ```
    function printSomething() {
        const args = Array.from(arguments);
        console.log(args);
    }

    printSomething('hi', 'hello');

    ```
