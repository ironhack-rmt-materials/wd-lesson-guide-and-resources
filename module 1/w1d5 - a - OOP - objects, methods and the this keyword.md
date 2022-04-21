
# OOP - objects, methods and the 'this' keyword


<!--

Status: draft

The exercise at the end (bakery) is worth doing.
The rest needs further work.


 -->

## Intro

- We've learned that we can use objects to store information:

  - Ex. 1:

    ```
    const student = {}
    ```



- But sometimes "things" have to be able to "do"

  - Student can "sayHello"

  - Can I save a function inside an object? --> Yes.

    ```
    const student = {
      sayHello: function() {
          console.log('hello');
      }
    };

    student.sayHello();

    ```

- OOP = Object-oriented programming (OOP) 


- "this" keyword
  - store studentName
  - display this.studentName

> "When invoking a method on an object, this becomes the object itself."





# ES6 Class Syntax:

- create multiple students that can "sayHello" (using plain objects)
  - problem: we repeat code

- old days: we used to do "prototype-based OOP"
- ES6: we use "classes"


- ES6 class with a method:
  - create a class and add a method
  - create a new "instance" of this class

```
class Student {
  sayHello() {
    console.log('hello');
  }
}

const alice = new Student();
const bob = new Student();

alice.sayHello();
bob.sayHello();
```

- instance
- constructor & this





# ES6 Class Syntax: Time to practice

Create a Bakery Class:

- Iteration 1: create a Bakery class with the following:
  - Name of our brand (will be the same one for all our bakeries)
  - Location (specific for each bakery we build)
  - method printLocation (displays the location of the bakery)

- Iteration 2:
  - Amount of cakes in stock (initial value: 0)
  - Functionality to bake one more cake (when that function is called, increase the amount of cakes by 1)
  - Functionality to display the amount of cakes in stock


- Iteration 3:
  - Money collected (initial value: 0)
  - Functionality to sell one cake (decrease stock & increases money by 3)

- Iteration 4:
  - When a cake is sold, we need to make sure there's actually stock

- (Bonus) Iteration 5:
  - Everytime a new cake is created, it costs 1 (deducted from the cash available)
  - Everytime a cake is sold, you collect 3
  - You can not make new cakes if there's no money
  - Initial cash: 2 [otherwise we can not start making cakes ;)]


Solution: https://stackblitz.com/edit/js-bewjfk?file=index.js

Time: 30min. in pairs

