
# JS - Async and Callbacks

<!--- 

Status: ready

Notes:
- we've introduced setTimeout() on w2d1, now we just need a few notes so that they can refresh and start the LAB


@todo:
- improve intro to synchronous vs. asynchronous code
- to do some cleanup & improve structure

--->



## Synchronicity vs. Asynchronicity



Synchronous way:
- prepare something to eat
- do the dishes
- organize your bedroom
- do whatever is next on your list.

Asynchronous way:
- order something to eat
- while waiting first clean all the dirty dishes
- then organize the room
- food is here

<!-- @Luis: improve this example -->


## Asynchronous Programming

- Async functions allow us to continue executing our code while the async function is being executed in the background. 

- Example:

    ```js
    console.log("cooking dinner...");

    setTimeout(function () {
        console.log("dinner's ready!!");
    }, 2000);

    for (let i = 1; i <= 5; i++) {
        console.log('washing dishes....' + i);
    }
    ```


- If the current script has not finished:

    ```js
    console.log('cooking dinner...');

    setTimeout(function () {
        console.log("dinner's ready!!");
    }, 200);

    //for loop with a lot of iterations...
    for (let i = 1; i <= 1000 * 1000; i++) {
        if (i % 1000 === 0) {
            console.log('washing dishes....' + i);
        }
    }
    ```


    > the function or code snippet cannot be executed until the thread that called setTimeout() has terminated.



- With a delay of 0 ms...

    ```js
    console.log('cooking dinner...');

    setTimeout(function () {
        console.log("dinner's ready!!");
    }, 0);

    console.log('washing dishes 1');
    console.log('washing dishes 2');
    console.log('washing dishes 3');

    ```

    > even though setTimeout was called with a delay of zero, it's placed on a queue and scheduled to run at the next opportunity; not immediately (currently-executing code must complete before functions on the queue are executed)




Synchronous: blocks code (ie. a line of code is not executed until previous one is completed)
Asynchronous: non-blocking



## JavaScript and (a)synchronicity

- "JavaScript is not an asynchronous language, but synchronous one with some asynchronous behaviors."

JavaScript is:
- single-threaded - only one block of code is executed at the time
- synchronous - the code gets executed line by line, from top to bottom, in the order in which they are put in.




## Callbacks II (further examples)


- Callback = when we pass a function as an argument to another function
  - example: `forEach()`
  - example: `setTimeout()`


- How else can be useful?


Initial example:

    ```js
        function cookDinner() {
            console.log('Preparing dinner...');
            console.log('Dinner is ready');
        }

        function eatDinner() {
            console.log('Eating dinner');
        }

        cookDinner();
        eatDinner();
    ```



But... dinner takes time to be prepared....


    ```js
    function cookDinner() {
        console.log('Preparing dinner...');
        setTimeout(function() {
            console.log('Dinner is ready');
        }, 1000);
    }

    function eatDinner() {
    console.log('Eating dinner');
    }

    cookDinner();
    eatDinner();

    ```

Options?
- add a delay in `eatDinner()`
  - problem: we need to know how much it takes to cook
- call `eatDinner()` from `cookDinner()`, once dinner is ready,
  - problem: cookDinner needs to know what to do once dinner is ready.


So we can pass it a function to be executed at the end (once dinner is ready)...

  ```js
  function cookDinner(myCallback) {
    console.log('Preparing dinner...');
    setTimeout(function() {
        console.log('Dinner is ready');
        myCallback();
    }, 1000);
  }

  function eatDinner() {
    console.log('Eating dinner');
  }

  cookDinner(eatDinner); //notice: we don't have ()

  ```



- IMPORTANT: 
  - when you're passing a function as a callback, make sure not to use ()


- When and why any function would be postponed/delayed in the real world?
  - Interact with the UI
  - Wait for some data from a database
  - Wait for some data that we get from a different server
  - ...



Practice: JS Callbacks

- Instructions: https://stackblitz.com/edit/js-graftg?file=index.js
- Time: 15min.

- Solution: https://stackblitz.com/edit/js-dzfqat?file=index.js



- (Extra) how to pass arguments

    ```js
    cookDinner(function(){ eatDinner("wine") });
    ```




## Refresh 

IMPORTANT: refresh some topics for today's lab (JS Chronometer):

- setTimeout + clearTimeout
- setInterval + clearInterval

- OOP 
  - refresh constructor
  - refresh properties (store any info that we need to access from different methods)

