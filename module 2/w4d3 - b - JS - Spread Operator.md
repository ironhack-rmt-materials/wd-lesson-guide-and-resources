# JS - Spread Operator

<!--- 

- Status: ready


-->




## Spread operator

- The spread operator:
  - lets us "unpack" / "spread" elements of an array/object into individual elements
  - can be used when all elements from an array/object need to be included in a list of some kind.



Examples using the spread operator:

  ```js
  const students = ["alice", "bob", "charlie"];
  const arrayTwo = ["julia", "leonardo", "brad", "sandra"];
  ```


- Example 1: Copy/clone arrays
  
  ```js
  const copy = [...students]; // (shallow copy)
  ```


- Example 2: Create a new array +  Add elements to it
  ```js
  const newArr = [...students, "david"]
  ```


- Example 3: Merge/Concatenate arrays

  ```js
  const newArr = [...arrOne, ...arrTwo]
  ```


- Example 4: with objects

  ```js
  const user = {
    company: 'Ironhacker',
    age: 25,
    favoriteMusic: 'Rock',
  };


  const superUser = {
    ...user,
    favoriteFood: "pizza"
  }

  console.log(superUser)
  ```


Practice: spread operator (& refresh forEach)
- https://stackblitz.com/edit/js-f87bqx?file=index.js
- Time: 10min.
- Solution: https://stackblitz.com/edit/js-t5ydb9?file=index.js





## (skip) Rest parameter


Example 1:

```js

  function greetUsers(user1, user2, ...otherUsers) {
    console.log(otherUsers);
  }

  greetUsers('alice', 'bob', 'charlie', 'david');

```


Example 2 (skip):

```js
  function add(...numbers) {
    // numbers represents the arguments passed when function gets invoked
    let sum = 0;
    for (let oneNumber of numbers) {
      sum += oneNumber;
    }
    return sum;
  }
  
  add(1); // 1
  add(1, 2); // 3
  add(1, 2, 5, 8); // 16
```


- (bonus) Exercise (practice rest parameters + arr.reduce): 
  - Instruction: https://stackblitz.com/edit/js-o9cpuo
  - How: groups of 2-3 students
  - Time: 15min.
  - Solution: https://stackblitz.com/edit/js-93eaiw?file=index.js





