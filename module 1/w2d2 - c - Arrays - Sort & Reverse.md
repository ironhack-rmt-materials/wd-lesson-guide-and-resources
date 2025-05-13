
# Arrays - Sort & Reverse

<!-- 
Status: draft (just some notes)
-->




## Cheatsheet:
- sort(): https://stackblitz.com/edit/ih-arr-sort?file=index.js

<!--
UPDATE: NOW WE HAVE DETAILED EXAMPLES OF .sort() IN THE FAQs
-->



## Important: sort() and reverse() mutate the original array
- They modify the original array
- Show how to create a copy.
  - e.g. `const copy = [...original]`

- Alternative: `arr.toSorted()`


## sort()

- Intro video - JavaScript Comparator Function Explained (12min.): 
  - https://www.youtube.com/watch?v=kxUNQtheCxM

- .sort() method sorts the elements of an array **in place** and returns the array.

- The default sort order is according to string **Unicode** code points.




### Sorting numbers

- First example (numbers below 10):

  ```js
    const numbers = [4, 1, 2, 3];
    numbers.sort();

    // [1, 2, 3, 4]
  ```

- Second example (numbers above 9):

  ```js
  const numbers = [20, 1, 2, 3];
  numbers.sort();
  
  // [1, 2, 20, 3]
  ```



- The items are sorted as strings by default
  - The method converts elements of the array into strings and then compares them.


- Example:

  ```js
  const numbers = [5, 6, 10, 20, 3];

  numbers.sort();

  console.log(numbers);

  ```


### Sorting strings

- Case sensitive: `arr.sort()`

- Case insensitive: https://stackoverflow.com/a/9645447/11298742



