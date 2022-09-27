

# JS - Data Types in JavaScript - Arrays


<!--- 

Status: highlighted

-->



## Topics:

- What / Why 

    > Arrays are data structures that allow us to group a collection of elements together in one variable.


- How to create an array (syntax)

  const arrayNames = ['Pedro', 'Jake', 'Joan', 'Mike'];

- Data Types
  - we can store any valid Data Type
  - note: can store different data types 
    -  const arrayNames = ['Pedro', 2, true];


- Accessing Elements
  - By index (Zero-Indexed)
  - `.length` property
  - Note: If we try to access an index that does not exist, it will return `undefined`


- Adding Elements: `.push()`

- Push vs. pop vs. unshift vs. shift:
  - https://vishalkukreja.com/wp-content/uploads/2021/03/2-1024x536.png


- Removing / Modifiying elements in the middle of the array: `.splice()`
  <!-- @LT: briefly -->

  ```
  array.splice(start, deleteCount)
  splice(start, deleteCount, item1, item2, itemN)
  ```
  - start: Index at which to start changing the array
  - deleteCount: number of old array elements to remove


- Iterate through arrays:
  - for loop
  - forEach ++++++


Exercise forEach (basic exercise with an array of strings):
- original instructions: https://stackblitz.com/edit/js-ymq3mb?file=index.js
- possible solution: https://stackblitz.com/edit/js-grgtur?file=index.js
- (extra bonus): practice with different loops (for loop, for...of,....)



- String `.split()` (briefly)
  
  > The split method allows us to separate a string into pieces and will return all the pieces as elements of a new array.

  - Syntax: `.split(separator)`
  

  - Example: 

    ```javascript
    const message = "i love pizza";
    const mailAddress = "bob@ironhack.com";

    const letters = msg.split(''); // split in characters (empty string)
    const words = msg.split(' '); // split in words (blank space)

    const info = mailAddress.split('@');

    ```

