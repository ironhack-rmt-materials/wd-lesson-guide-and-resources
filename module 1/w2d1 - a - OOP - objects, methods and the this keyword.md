
# OOP - objects, methods and the 'this' keyword


<!--

Status: ready

-->



## Intro

- We've learned that we can use objects to store information:

  - Ex. 1:

    ```js
    const user = {
      userName: "Alice",
      age: 30,
      languages: ["english", "french"]
    }
    ```



- But sometimes "things" have to be able to "do"

  - User can "sayHello"

  - Can I save a function inside an object? Yes.

    ```js
      const user = {
        sayHello: function() {
            console.log('hello');
        }
      };

      user.sayHello();
    ```

- OOP = Object-oriented programming (OOP) 


- "this" keyword
  - add property `userName`
  - display `this`
    - `console.log(this);`
  - display `this.userName`

> "When invoking a method on an object, this becomes the object itself."





# ES6 Class Syntax:

- create multiple users that can "sayHello" (using plain objects)
  - problem: we repeat code

- old days: we used to do "prototype-based OOP"

- ES6 Classes (introduce the syntax)

  ```js 
  class MyClass {
    constructor(){

    }
    doSomething(){

    }
    doSomethingElse(){

    }
  }
  ```



- ES6 class with a method:
  - create a class and add a method
  - create a new "instance" of this class

    ```js
    class User {
      sayHello() {
        console.log('hello');
      }
    }

    const alice = new User();
    const bob = new User();

    alice.sayHello();
    bob.sayHello();
    ```


  - Advantage (compared to plain objects):
    - Code reusability: now we can create multiple "instances" with shared functionality without repeating code.



- Instance


- Constructor + storing info in properties

  <!-- @LT: do not add "age" (we will do it in an exercise)  -->


    ```js
    class User {
      constructor() {
        console.log('the constructor method was invoked');
        const userName = 'alice';
        //this.userName = 'alice';
      }
      sayHello() {
        console.log('hello, my name is...' + this.userName);
      }
      sayGoodbye() {
        console.log('goodbye, my name is...' + this.userName);
      }
    }

    const userOne = new User(); // create a new instance
    userOne.sayHello();
    userOne.sayGoodbye();

    ```

- Passing arguments to the constructor()


    ```js
    class User {
      constructor(userName) {
        this.userName = userName;
      }
      sayHello() {
        console.log('hello my name is ' + this.userName);
      }
      doSomething() {
        console.log("i'm doing something");
      }
    }

    const user1 = new User('Bob');
    user1.sayHello();
    ```


- Properties vs. local variables
  - you can declare a variable inside a method
  - you can also use properties to store information
    - We use properties to store information that belongs to the whole instance
    - Properties can be accessed from all methods.




## Practice: OOP - properties & the keyword `this`


Initial Code: https://stackblitz.com/edit/js-tjmjh1?file=index.js

1. Add functionality for "age"
  - store the age of the user
  - when the user says hello, display: `hello, my name is xxx and I am xxx years old`

2. (bonus) Add a method getOlder()
  - when called, this method would increase age by one.

3. (bonus) Every time the user gets older, call sayHello

Solution: https://stackblitz.com/edit/js-yzcuvt?file=index.js

- How: Individual.

- Time: 15min + 5min (compare the solution with your own & read notes). 




- Disclaimer: storing age vs. birth date (it is a good time to introduce JS dates)
  - create a date object

    ```js 
    const now = new Date();
    console.log(now);
    ```


  - create a date object with a specific date

    ```js
    const birthDate = new Date('1984-06-14');
    console.log(birthDate);

    ```


  - date methods. Ex: 
    
    ```js
    const birthDate = new Date('1984-06-14');

    const monthIndex = birthDate.getMonth();
    const monthName = birthDate.toLocaleString('default', { month: 'long' });

    console.log(monthIndex);
    console.log(monthName);

    ```

  
  - MDN:
    - https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/Date




## Practice: ES6 Classes (OOP Bakery)


Instructions: 
- https://gist.github.com/luisjunco/c7ea4d03c6db5c6923e5b767e6935ca1


Solutions: 
- link to solutions is included in that gist.


Time: 30min. in pairs




## (Bonus) Pair Maker Exercise

Create a class "Cohort" with:
- information of all students in our class (for each student, we just need to store the name -ex. "alice", "bob", "charlie").
- functionality to select one student randomly
- functionality to create random pairs
- (bonus) if we try to generate pairs with an odd number of students, create a group of three.
- (bonus) functionality to create groups of any given size (ex. groups of 3, groups of 4, 5, 6, 7....).


- Time: 1-5h.

- Possible solution: https://stackblitz.com/edit/js-i6h4lc?file=index.js




## (skip) Alternative syntax for Class Fields

  ```js
  class User {
    age = 20;
    energy = 1;

    //...
  }
  ```

Example: https://stackblitz.com/edit/js-twnm88?file=index.js





## (skip) Private Properties & Methods (#)

> Private properties and methods are accessible only within the class and not from the outside. They are used to encapsulate certain properties and methods of the class.


> To define a private property or method, we use the # symbol followed by the name of the property or method.


Example:

```js
class BankAccount{

  #balance; // create a private property

  constructor(initialBalance, accountHolder){
    this.#balance = initialBalance;
    this.accountHolder = accountHolder;
    this.#increaseBalance(); // can invoke private methods within the class ✅
  }

  #increaseBalance(){
    this.#balance += 50;  // can access private properties within the class ✅
  }
  
  displayBalance(){
    console.log(this.#balance)
  }
}

const account = new BankAccount(1000, "alice");

// account.#balance = 5000; // can not access properties from outside ❌
// account.#increaseBalance(); // can not invoke methods from outside ❌

account.displayBalance();
```

