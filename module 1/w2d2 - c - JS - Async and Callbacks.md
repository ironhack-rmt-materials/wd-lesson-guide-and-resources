
# JS - Async and Callbacks

<!--- 

Status: ready

Notes:
- we've introduced setTimeout() on w2d1, now we just need a few notes so that they can refresh and start the LAB



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




## Asynchronous Programming

- Async functions allow us to continue executing our code while the async function is being executed in the background. 

- Example:

    ```js
    console.log("cooking dinner...");

    setTimeout(function () {
        console.log("dinner's ready!!");
    }, 3000);

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



## JavaScript and (a)synchronicity

- "JavaScript is not an asynchronous language, but synchronous one with some asynchronous behaviors."

JavaScript is:
- single-threaded - only one block of code is executed at the time
- synchronous - the code gets executed line by line, from top to bottom, in the order in which they are put in.



## Refresh 

Concepts:
- "callback"
- setTimeout + clearTimeout
- setInterval + clearInterval



IMPORTANT: refresh some topics for today's lab (JS Chronometer):
- OOP 
  - refresh constructor
  - refresh properties (store any info that we need to access from different methods)

