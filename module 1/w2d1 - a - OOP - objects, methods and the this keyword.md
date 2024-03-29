
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

3. (bonus) Everytime the user gets older, call sayHello

Solution: https://stackblitz.com/edit/js-yzcuvt?file=index.js

- How: Individual.

- Time: 15min + 5min (compare the solution with your own & read notes). 




- Disclaimer: storing age vs. birthdate (it is a good time to introduce JS dates)
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

<!--
@todo:
- improve instructions/wording
  - rename to "display" instead of "print"
- create gist.
-->


- Iteration 1: create a Bakery class with the following information and functionality:
  - property "brandName", which needs to be the same one for all our bakeries (ie. for all instances of the Bakery class)
  - property "location" (specific for each bakery we build)
  - method "printLocation" (displays the location of the bakery)

- Iteration 2: we will add functionality to bake cakes & keep track of the number of cakes we have.
  - Store information about the amount of cakes in stock (initial value: 0)
  - Add functionality to display the amount of cakes in stock
  - Add functionality to bake one more cake (when that function is called, we need to increase the amount of cakes by 1). After you bake a cake, you can display the number of cakes in stock (reuse the function that you already have).


- Iteration 3:
  - Money collected (initial value: 0)
  - Functionality to display the money we have
  - Functionality to sell one cake (decrease stock & increases money by 3)

- Iteration 4:
  - We shouldn't sell a cake if we don't have cakes, right?
  - Hint: when a cake is sold, make sure there's actually stock ;)

- (Bonus) Iteration 5: let's apply some real life economics...
  - Everytime a new cake is created, it costs 1 (deducted from the cash available)
  - Everytime a cake is sold, you collect 3
  - You can not make new cakes if there's no money
  - Initial cash: 2 -we need some initial investment, otherwise we can not start making cakes ;)


Solution: https://stackblitz.com/edit/js-kftsnf?file=index.js

Time: 30min. in pairs




## (Bonus) Pair Maker Exercise

Create a class "Cohort" with:
- information of all students in our class (for each student, we just need to store the name -ex. "alice", "bob", "charly").
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



