
# JS - OOP - class and inheritance

<!-- 
  status: draft 
  to-do: improve example
  to-do: create slides (oop principles)
-->



- Class is like a blueprint:
  https://media.istockphoto.com/vectors/blueprint-of-building-vector-id510230824?k=6&m=510230824&s=612x612&w=0&h=1RqJkSYJX_Cpb-ygITjIFURs1aSivP4ImepMYzN7NGU=


- Intro OOP Principles (for now, just mention them): 
  - https://www.learncomputerscienceonline.com/wp-content/uploads/2021/01/Principles-Of-Object-Oriented-Programming.jpg


- Inheritance
  - example:
    - Class "Animal"
      - property `species`
      - property `location`
      - method `sayHello`:
        - `hello, I am a ${this.species} living in ${this.location} `

    - "Dog" extends "Animal"
      - property `name`
      - method `bark()`
      - method `sayHello()` (dogs say hello in a different way)

    - example: https://stackblitz.com/edit/js-jeyw5h?file=index.js

    <!-- @todo: improve this example -->


  - concepts:
    - extends
    - super()
    - polymorphism (example: Method Overriding)


  - Further improvements:
    - Animals can have `energy`
    - functionality to `move` (dicreases energy)
    - functionality to `eat` (increases energy)

    <!-- 
    
    @todo: 
    - improve this example 
    - prepare quick exercise with inheritance
    
    -->



- (Extra) further examples with inheritance & super:
  - Video: JavaScript super keyword 🦸‍♂️ (Bro Code, 7min.)
    https://www.youtube.com/watch?v=khuDeNwXkfI

    <!-- 
    
    Person
    - Student
    - Teacher

    Includes:
    - super();
    - super.hello();
    
     -->


- OOP principles:
  - inheritance
  - abstraction
  - polymorphism 
  - encapsulation



# Time to practice

Coffee Shop:
- A Coffee Shop is a special kind of Bakery that, apart from cakes, it also serves coffee: extend your previous Bakery Class.


