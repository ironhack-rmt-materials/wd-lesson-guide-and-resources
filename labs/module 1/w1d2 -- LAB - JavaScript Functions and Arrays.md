# LAB | JavaScript Functions and Arrays

[REPO](https://github.com/ironhack-labs/lab-javascript-functions-and-arrays)

[SOLUTION](https://gist.github.com/IH-WebDev-TA-Remote/31196f40d9eef74f02860a62842f30d8)

### REMIND

- Fork
- Clone
- git add, commit, push

- PR
- submit LAB on SP -> share PR!! Not github link !

### Guidelines for LAB

- automated testing. Jest is an automated test-runner for JavaScript.

-  go into labs directory 
    - npm install. npm is the package manager for JS -> It holds dependencies
    - npm run test:watch -> will create html file


- LiveServer extension. Open ONLY html file
- test suite  + tests (just write the function, do not need to call it)

## TIPS

- LiveServer extension. Open ONLY html file
- do not change function names!!
- if test crashes - there is error in code!! Tests are working - your code isn't ;) 
- console.log() appears at the bottom of browser page
- the name you pass into function is the one you use inside !! 
    - WATCH SCOPE 
    - keep code inside function scope
- if task not clear - look at tests
- function has to be reusable (no specific data inside)

### ITERATIONS

- iterations vs bonuses 

- iteration 4. Reuse the function for sum
- iteration 5. Want to create new array and add values there
- iteration 6 & 7. Pass two arguments

### Example

```
let num1 = 5;
let num2 = 4;

function bigger(a, b) {
  if (num1 > num2) {
    return num1
  } else {
    return num2
}
```