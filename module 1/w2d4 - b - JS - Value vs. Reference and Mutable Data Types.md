

# JS - Value vs. Reference and Mutable Data Types


<!-- 

Status: ready

-->


- Intro: mutating arrays

  - Example 1:

    ```js

      const amount = 10;
      amount = 20;

      const numbers = [10, 10, 10];
      numbers[0] = 20;

    ``` 


  - Other examples (mutating arrays):

    ```js
      numbers.push(50); //mutates the original array
      numbers.reverse(); //mutates the original array

    ``` 



- Why it happens

  - Primitive data types are stored (and copied) by value
  - Non-Primitive data types are stored (and copied) by reference.


- Slides:
  - https://docs.google.com/presentation/d/1BIgfKvQq6lR8QaSBmscUROQ961-ZbgzY6XDMdToqShY/edit?usp=sharing




- Example 1 (comparing variables):

  ```js
    const name1 = "alice";
    const name2 = "alice";

    if(name1 === name2){
      console.log("same string");
    } else {
      console.log("different string");
    }



    const array1 = ["alice", "bob", "charlie"];
    const array2 = ["alice", "bob", "charlie"];

    if(array1 === array2){
      console.log("same array");
    } else {
      console.log("different array");
    }

  ``` 



- Example 2 (modifying a copy):

  ```js

    let amount = 10;

    let amountCopy = amount;
    amountCopy = 20;

    console.log(amount);
    console.log(amountCopy);


    //

    const numbers = [10, 10, 10];
    const copy = numbers;
    copy.push(50);

    console.log(numbers);
    console.log(copy);

  ``` 


  > since both objects or arrays are pointing to the same address in the memory (have the same reference), changes in one will cause the same changes in the other one as well.



- IMPORTANT: all this examples are with arrays but the same applies to objects.


  
- If we don't want to mutate the array, we can make a copy (copy the values)
  - ex. use a for loop

  <!-- @LT: create a new stackblitz project -->

  ```js
  const numbers = [1, 2, 3];
  const numbersCopy = [];

  for (i = 0; i < numbers.length; i++) {
    const value = numbers[i];
    numbersCopy.push(value)
  }
  ```


- Explain: Shallow vs. deep copy 

  ```js
  // Shallow copy
  //  --> we copy the top-level by value
  //  --> but, if we have nested levels, they're still copied by reference

  // Deep copy --> we copy all levels by value (including nested levels)
  ```

- Make a quick example of shallow copy (with nested data structure)


## How to clone arrays/objects

Summary & examples: https://stackblitz.com/edit/js-ecmhxh?file=index.js

<!-- @todo: create cheatsheet (ex. gist with a table of common ways) -->


### How to clone an array

- Shallow copy: `const ironhackers = [...students];`
- Deep copy 1: `JSON.parse(JSON.stringify());`
- Deep copy 2: `const copy = structuredClone(original);`


### How to clone an object

- Shallow copy: `const userCopy = { ...user };`
- Deep Copy 1: `JSON.parse(JSON.stringify( myObject ));`
- Deep Copy 2: `const copy = structuredClone(original);`


  - (skip) Object.assign:

    ```js
    const book2 = Object.assign({}, book1); // shallow copy
    ```




Note: 
- there's many different ways to clone arrays and objects
  - ex. https://www.freecodecamp.org/news/how-to-clone-an-array-in-javascript-1d3183468f6a/
- you don't need to know them. Just make sure:
  - understand the fundamentals.
  - know how to create a shallow and a deep copy
  - if you come across a syntax that you don't understand, you may need to do some research.
    - Example:

      ```js
      const numbers = [10, 20, 30];
      const n = [].concat(numbers); // someone chose a poor name for the variable, we need to find out what this line does.
      ``` 

