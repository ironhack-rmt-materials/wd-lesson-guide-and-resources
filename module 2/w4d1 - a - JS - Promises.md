
# ES6 - Promises

<!--

- Status: draft 

- Also highlighted (WDFT+202107_RMT)

- Note: 
  - Students find the lab a bit difficult (esp. iteration 2). Give them a similar example so that they can compare with.
  - Iteration 2: remind them also that the function needs to 'return' a new promise

-->



## Intro

- Why promises ("Callback hell")

  - v1: Start from basic example: cookDinner() + eatDinner()

    ```javascript
    function cookDinner() {
        console.log('dinner ready');
    }

    function eatDinner() {
        console.log('eating dinner');
    }

    cookDinner();
    eatDinner();

    ```

  - v2: add timout + callback

  - v3: add serveTheTable(): now we have to call a function passing a callback and inside another callback.... 

    ```javascript
    function cookDinner(callback) {
    setTimeout(() => {
        console.log('dinner ready');
        callback();
    }, 2000);
    }

    function serveTheTable(callback) {
    setTimeout(() => {
        console.log('table ready');
        callback();
    }, 1000);
    }

    function eatDinner() {
    console.log('eating dinner');
    }

    cookDinner(function() {
        serveTheTable(eatDinner);
    });

    ```


- Example final code: https://stackblitz.com/edit/js-sysuje?file=index.js
  - cookLunch > serveTheTable > callMyFamily > eatLunch
  


- Callback Hell (search images)





## ES6 promises intro

- Promise object represents the eventual completion (or failure) of an asynchronous operation and its resulting value.

- Advantage: code easier to read and maintain.
  - Callback hell vs. vertical code: https://miro.medium.com/max/1838/1*AqkCUN-kD_fLefEFPnX2Uw.png




## Possible states of a Promise object

- `pending`: initial state, neither fulfilled nor rejected.
- `fulfilled`: meaning that the operation was completed successfully.
- `rejected`: meaning that the operation failed.

https://www.javascripttutorial.net/wp-content/uploads/2020/03/JavaScript-Promise-state.png


- Note: a Promise can only be `settled` (fulfilled or rejected) once.



## Creating Promises


```javascript
function doSomething(){
  const myPromise = new Promise(function(resolve, reject) {
    if (/* condition */) {
        resolve(/* value */);  // fulfilled successfully
    }
    else {
        reject("message");  // error, rejected
    }
  });

  return myPromise;
}

```



## Consuming Promises

```javascript
    const p = new Promise((resolve, reject) => resolve('Ironhack'));
    p.then((val) => console.log(val)); // Ironhack
```

- A Promise’s .then() method actually takes two possible parameters.
  - The first is the function to be called when the Promise is fulfilled.
  - The second is a function to be called if the Promise is rejected.


Example: https://stackblitz.com/edit/js-jw7jql?file=index.js



## Chained Promises

- Each .then() returns a newly generated promise object, which can optionally be used for chaining

```javascript
aFunctionThatReturnsAPromise
.then(handleResolvedA)
.then(handleResolvedB)
.then(handleResolvedC)
.catch(handleRejectedAny);
```


Diagram: https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_9df97f56698a5721fa8b63445515c6e8.png




## Dealing with errors

```javascript
const p1 = new Promise((resolve, reject) => {
  if (true) throw new Error('rejected!');
  else resolve(4);
});

p1.then((val) => val + 2)
  .then((val) => console.log('got', val))
  .catch((err) => console.log('error: ', err.message));
// => error: rejected!

```




## Promises All

- Promise.all() method returns a single Promise that resolves when all of the promises in the iterable argument have resolved




## async/await

- Note: needed for the lab


## (extra) watch a youtube video together:

- JS promises in 100 Seconds: https://www.youtube.com/watch?v=RvYYCGs45L4

- JavaScript Promises In 10 Minutes (11:30): https://www.youtube.com/watch?v=DHvZLI7Db8E
  - Promises
  - Callback syntax
  - Promise.all()

- Async JS Crash Course - Callbacks, Promises, Async Await (24:30): https://www.youtube.com/watch?v=PoRJizFvM7s
  - Promises
  - Promise.all()
  - fetch()
  - aynct/await



## Code from previous courses:

- Consuming promises:
  - Initial example with callbacks:
    https://stackblitz.com/edit/js-m92ra4?file=index.js
  - Basic example with .fetch:
    https://stackblitz.com/edit/js-9hfrjq?file=index.js
  - Basic example of Consuming and Chaining promises with .then().catch()
    https://stackblitz.com/edit/js-4hdgpr?file=index.js
  - Consuming promises with .then().catch() & Promise.all()
    https://stackblitz.com/edit/js-az5e4a?file=index.js
  - Consuming promises with Async/await
    https://stackblitz.com/edit/js-2qc8xw?file=index.js

- Creating promises:
  - initial code with callbacks:
    https://stackblitz.com/edit/js-m92ra4?file=index.js
  - CREATING PROMISES and consuming with .then().catch()
    https://stackblitz.com/edit/js-vemwgp?file=index.js
  - CREATING PROMISES and consuming with async/await
    https://stackblitz.com/edit/js-ftozmy?file=index.js

- Callback pattern vs. Promises vs. Async/Await
  https://stackblitz.com/edit/js-ifcwpk?file=index.js