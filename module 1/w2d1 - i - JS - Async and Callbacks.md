
# JS - Async and Callbacks

<!--- 

Status: ready

Notes:
- we've introduced setTimeout() on week1, now we just need a few notes so that they can refresh and start the LAB



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


## JavaScript and (a)synchronicity

- "JavaScript is not an asynchronous language, but synchronous one with some asynchronous behaviors."

JavaScript is:
- single-threaded - only one block of code is executed at the time
- synchronous - the code gets executed line by line, from top to bottom, in the order in which they are put in



## Asynchronous Programming

- Async functions allow us to continue executing our code while the async function is being executed in the background. 

- Example:

    ```
    setTimeout(function () {
    console.log("dinner's ready!!");
    }, 3000);

    for (let i = 1; i <= 12; i++) {
    console.log('washing dishes....' + i);
    }
    ```


Concepts:
- "callback"
- setTimeout + clearTimeout
- setInterval + clearInterval


