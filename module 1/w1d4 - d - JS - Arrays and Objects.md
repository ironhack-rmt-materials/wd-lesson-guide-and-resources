

# JS - Arrays & Objects

<!--- 

Status: draft


Consider: 
- this unit can be recorded (self-guided).
- or, prepare a self-guided exercise with hints (can be done in pairs)

-->



## Data structures
- The better we can organize our data → The better we can represent reallity → better code.


- Examples:

```js
const employees = ['alice', 'bob', 'charly'];

const company = {
  name: 'mama mia pizza restaurant',
  cash: 20
};
```




## Nested data structures:

- object that includes an array

  ```js
  const user = {
    name: "alice",
    languages: ["french", "english"]
  }
  ```

- object that includes an object --eg. company with address

  ```js
  const company = {
    name: 'mama mia pizza restaurant',
    cash: 20,
    address: {
      town: "berlin",
      postCode: "09x2"
    }
  };
  ```

- array of arrays (aka. "two-dimensional array")
  - ex: array of classes (each class is an array of student names)

  ```js
  const school = [
    ['alice', 'bob', 'charly'],
    ['pikachu', 'wonderwoman', 'superman'],
  ];
  ```


- array of objects 
  - ex: array of students

  ```js
  const students = [
    { name: 'alice', city: 'paris' },
    { name: 'bob', city: 'berlin' },
    { name: 'charly', city: 'madrid' },
  ];
  ```



## Reading data from nested data structures
- practice


## Updating data
- practice


## Adding data
- practice: add a new element at the end of the last class (push)



## (bonus) Practice: nested data structures

- Instructions: https://stackblitz.com/edit/js-kca4fv?file=index.js
- Time: 20min.

- Solution: https://stackblitz.com/edit/js-knwk8d?file=index.js




