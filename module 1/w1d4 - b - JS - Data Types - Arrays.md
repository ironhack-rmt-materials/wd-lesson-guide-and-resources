

# JS - Data Types in JavaScript - Arrays


<!--- 

Status: ready

-->



## Topics:

- What / Why 

    > Arrays are data structures that allow us to group a collection of elements together in one variable.


- How to create an array (syntax)

  ```js
  const user1 = "alice"
  const user2 = "bob";
  const user3 = "charly";

  const users = ["alice", "bob", "charly"];
  ```

- Data Types
  - we can store any valid Data Type
  - note: can store different data types 
    ```js
    const arrayNames = ['alice', 2, true];
    ```


- Accessing Elements
  - By index (Zero-Indexed)
  - Note: If we try to access an index that does not exist, we will get `undefined`

- Arr length:
  - `.length` property
  - diagram (index and length): https://i.imgur.com/BG4RUNt.png



- Adding Elements: `.push()`
- Removing (from the end): `.pop()`

- push() vs. pop() vs. unshift() vs. shift()
  - https://vishalkukreja.com/wp-content/uploads/2021/03/2-1024x536.png
  <!-- covered in prework, can do briefly -->




- Add / Remove / Modify elements in the middle of the array: `.splice()`
  <!-- @LT: briefly -->

  ```js
  arr.splice(start, deleteCount)
  arr.splice(start, deleteCount, item1, item2, itemN)
  ```
  - start: Index at which to start changing the array
  - deleteCount: number of old array elements to remove




Iterate through arrays:

- for loop
  - demo (ask a student to help me)
  - note: some students still struggle with this, go slowly

- forEach ++++++
  - `const menu = ["pizza", "salad", "pasta", "falafel"]`


Practice: forEach
<!-- (with an array of strings): -->
- Instructions: https://stackblitz.com/edit/js-ymq3mb?file=index.js
- Time: 15-20min.
- Solution: https://stackblitz.com/edit/js-grgtur?file=index.js


  <!-- @todo: create cheatsheet forEach() -->




## (skip) String `.split()`
  
  <!-- 
  
    @LT: skip or very brief
  
    (they don't need it for today's lab)

  -->


  > The split method allows us to separate a string into pieces and will return all the pieces as elements of a new array.

  - Syntax: `.split(separator)`
  

  - Example: 

    ```js
    const msg = "i love pizza";
    const mailAddress = "bob@ironhack.com";

    const letters = msg.split(''); // split in characters (empty string)
    const words = msg.split(' '); // split in words (blank space)

    const info = mailAddress.split('@');

    ```

