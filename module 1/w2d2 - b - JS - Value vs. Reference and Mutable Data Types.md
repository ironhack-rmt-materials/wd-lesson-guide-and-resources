
# JS - Value vs. Reference and Mutable Data Types




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








  - Example 3 (comparing variables):

    ```js
      const name1 = "alice";
      const name2 = "alice";

      if(name1 === name2){
        console.log("same string");
      }  else {
        console.log("different string");
      }



      const array1 = ["alice", "bob", "charly"];
      const array2 = ["alice", "bob", "charly"];

      if(array1 === array2){
        console.log("same array");
      } else {
        console.log("different array");
      }

    ``` 



  - Example 4 (modifying a copy):

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

    - visual explanation (fill cup): 
      - https://res.cloudinary.com/practicaldev/image/fetch/s--CHOh2r59--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/00irkh2jsmre37ngzdgt.gif



-  IMPORTANT: all this examples are with arrays but the same applies to objects.


  

- If we don't want to mutate the array, we can make a copy (copy the values)
  - ex. use a for loop

  ```js
  numbers = [1, 2, 3];
  numbersCopy = [];

  for (i = 0; i < numbers.length; i++) {
    const value = numbers[i];
    numbersCopy.push(value)
  }
  ```


- Explain: Shallow vs. deep copy



<!-- Note: different options to clone arrays/objects can be self guided -->


## How to clone an object

  - Deep Copy: `JSON.parse(JSON.stringify( myObject ))`

  - Note: there's many other ways. Ex.:

    ```js
    const book2 = Object.assign({}, book1); // shallow copy
    ```




## How to clone an array
- Shallow copy: `const ironhackers = [...students];`
- Deep copy: `JSON.parse(JSON.stringify())`


Note: 
- there's many different ways to clone arrays and objects
  - ex. https://www.freecodecamp.org/news/how-to-clone-an-array-in-javascript-1d3183468f6a/
- you don't need to know them. Just make sure:
  - understand the fundamentals.
  - know how to create a shallow and a deep copy
  - if you come accross a syntax that you don't understand, you may need to do some research.
    - Example:

      ```js
      const numbers = [10, 20, 30];
      const n = [].concat(numbers); // someone chose a poor name for the variable, we need to find out what this line does.
      ``` 




## Summary

Some options to clone arrays and objects
  - https://stackblitz.com/edit/ih-arr-sort-us6skb?file=index.js



