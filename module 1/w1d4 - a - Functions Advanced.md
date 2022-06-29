

# Functions Advanced


<!--- 
    Status: complete
--->


## Intro


- We've already seen how we can declare & use functions

    ```
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

> example ("a function can be passed to other functions"): **forEach()**


## Function Expressions

- We know that we can store a function in a variable

- Example:

    ```
    const calcSum = function(x, y) {
        return x + y;
    };

    calcSum(2, 3);
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

```
  setTimeout(function () {
    console.log('done!');
  }, 1000);
```

- Interval


- Clearing timeout / interval
  - clearTimeout()
  - clearInterval()



## Callbacks

- A function can be passed as an argument to another function
  - example: `forEach()`
  - example: `setTimeout()`


- How else can be useful?

Initial example:

    ```
        function cookDinner() {
            console.log('Preparing dinner...');
        }

        function eatDinner() {
            console.log('Eating dinner');
        }

        cookDinner();
        eatDinner();
    ```

> but **dinner takes time to be prepared**:


    ```
    function cookDinner() {
        console.log('Preparing dinner...');
        setTimeout(function() {
            console.log('Dinner's ready');
        }, 1000);
    }

    function eatDinner() {
    console.log('Eating dinner');
    }

    cookDinner();
    eatDinner();

    ```


> so we can pass it a function to be executed at the end (once dinner is ready):

  ```
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


- **IMPORTANT: when you're passing a function as a callback, make sure not to use ()**
  - (with parenthesis, you're actually passing the result of calling that function)


- When and why any function would be postponed/delayed in the real world?
  - Interact with the UI
  - Wait for some data from a database
  - Wait for some data that we get from a different server
  - ...



- Check for understanding:

```
    function saveUserInformation() {
    // saving information in the database
    // that usually takes a few seconds...
    }

    function displayConfirmationMessage() {
    // display a confirmation message
    }
```


## Anonymous functions

- An anonymous function is a function without a name.

- Why ?
  - if it will be used just in that very moment and never again in your code

- Example:
  - call setTimeout
    - pass a function created with a function declaration / function expression
    - pass an anonymous function


## Arrow Functions
- Alternative syntax to a traditional function expression, 
- (they're a different way to create functions)
- Introduced with ES6

- Example:
```
  // function expression syntax
  const greeting = function(name) {
    console.log(`Hello, ${name}!`);
  };

  // arrow function syntax
  const greeting = (name) => {
    return name;
  };

```

- when we can ommit parenthesys (only one arg)
- when we can ommit curly braces (only one line)

- "Normal" vs "Arrow" functions
  - quite much the same
  - in some cases we'll need to use one or the other (scope / this)





## Practice: different ways of creating functions (+ delays & callbacks) 

Time: flexible 
-- iteration 1 is great to practice (10min)
-- iteration 3 challenging for many students (10% completed after 20min)

We will practice:
- different ways to create functions
  - function declaration
  - function expression
  - arrow function
- anonymous functions
- delays & callbacks

```
    //
    // My morning routine:
    //
    //
    // Iteration 1:
    //
    // - Create the functions below:
    //   1. wakeUp(): use a function statement
    //   2. prepareCoffee(): use a function expression
    //   3. drinkCoffee(): use an arrow function expression
    //
    // - Each function will just print a message on the console
    // (eg. "Good morning", "Coffee is ready", "Drinking coffee" 
    //
    // - Call (invoke) those functions, one after each other
    //
    //
    // Iteration 2:
    // - Prepare coffee takes 3 seconds (we will now display the message after 3 secs.). 
    // - For this iteration, it's ok if you're drinking coffee without being ready ;)
    //
    // Iteration 3:
    // - Drink coffee only once it is ready (the function prepareCoffee() now expects to receive a callback and will execute it once coffee is ready)

```

Solution: https://stackblitz.com/edit/js-mpq4jv?file=index.js


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
