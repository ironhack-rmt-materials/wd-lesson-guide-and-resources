
# JS - Variable scope, hoisting and shadowing


<!--- 

Status: ready

Consider: including closures.

--->



## Scope


- Scope === the region of the program where a particular variable is accessible



- Example: 

  ```js
    function doSomething() {
      const amount = 3;
    }

    doSomething();

    console.log(amount);

  ```



REMEMBER: 
- from a child scope, you have access to variables in the parent scopes, but
- from the parent scope, you don't have access to variables in the child scope



- 3 types of scope:
  - Global
  - Function
  - Block scope


    Global:
    > A variable with global level scope is accessible from anywhere within the script where it was created (after it has been created).

    Function level scope:
    > limited to within the function from which it was declared and any child scopes such as nested functions or statements.

    Block level scope:
    > limited further to the statement or expression of which the variable was declared. 


REMEMBER (again):
- child scopes have access to parent scopes, but not vice versa.



With functions:
- inner functions (/blocks) can access outer variables (outerVar). 
- outer functions (/blocks) can't access the inner variables (innerVar).



var vs let/const:
- var: global / function scope
- let & const: global / function scope / block scope



Example 1:

  ```js
  let outerVar = 1;

  function doSomething() {
    let innerVar = 2;
    console.log(outerVar);
  }

  doSomething();
  console.log(innerVar); // => ReferenceError: innerVar is not defined
  ```



Example 2:

  ```js
  for (let i = 1; i <= 3; i++) {
    console.log(`Iteration number: ${i}`);
  }
  
  console.log(`After the loop: ${i}`);
  ```




## Shadowing

Variable shadowing:
  - when a variable declared within a certain scope has the same name as a variable declared in an outer scope.
  - ie. variables with the same name in different scopes.


Example 1:


  ```js
  let ironhacker = "alice";

  if(true){
    let ironhacker = "bob";
    console.log(`Name INSIDE if statement: ${ironhacker}`);
  }

  console.log(`Name OUTSIDE if statement: ${ironhacker}`);
  ```

> When JavaScript sees a reference to a variable, it will try to find the variable declaration within the same scope where it has been referenced. If it can't find that declaration, it will look for it within the parent scope. If it can't find it there, it will look for the grand-parent scope… and will keep trying until it reaches the global scope.



- Bonus: in the previous example....
  replace `let ironhacker = "bob";`
  with `ironhacker = "bob";`





Example 2 (ask students):

  ```js
    let a = 1;
    let b = 2;

    function sayHello() {
      a = 4;
      let b = 3;
    }

    sayHello();
    console.log("a..." + a);
    console.log("b..." + b);
  ```


  Explanation: 
  ```js
    a = 4; // reassigned
    let b = 3; // declared in an inner scope
  ```





## Hoisting 


- Hoisting is a JavaScript mechanism where variables and function declarations are moved to the top of their scope before code execution.


- functions declared with `function` keyword are hoisted

  ```js
    doSomething();

    function doSomething() {
      console.log('doing something');
    }
  ```



<!--

- skip variable hoisting (we will always use let/const)

-->

- (skip) var and hoisting:
  - Variables declared using var are moved to the top if it's scope (we say - hoisted) and initialized with a value of undefined.

  - Example:

    ```js
      console.log(message); // => undefined
      var message = 'Hello from the global scope!';
    ```


- (skip) let/const and hoisting:

  - let and const hoist, but you can't access them before the actual declaration is evaluated at runtime.

  - Example:

    ```js
      console.log(message); // => ReferenceError: Cannot access 'message' before initialization
      let message = 'Hello from the global scope!';
    ```







## Global Object pollution

- Avoid polluting the global scope





## Quiz

What's the output for the following examples?


**Example 1:**

```js
let username = 'alice';

function myFunc() {
  username = 'bob';
}

myFunc();
console.log(username);
```




**Example 2:**

```js
let username = 'alice';

function myFunc() {
  let username = 'bob';
  let username = 'charlie';
  console.log(username);
}

myFunc();
console.log(username);
```

A: Error: Identifier 'username' has already been declared
Q: what is the output if we comment "charlie" ?




**Example 3:**

```js
for (let count = 0; count < 5; count++) {
  console.log(count);
}

console.log('final: ', count);
```

<!-- Note: can also show using `var` (doesn't have block scope) instead of `let` -->




**(skip) Example 4:**

```js
  for(var counter = 0; counter< 5; counter++){
    setTimeout(() => console.log(counter), 1000)
    // setTimeout(() => console.log(counter))
  }
```

A:  5 (x5 times)

Q: (SKIP) Can you make the output of the above question as sequential like 0,1,2,3,4 instead of 5 (5 times)?






