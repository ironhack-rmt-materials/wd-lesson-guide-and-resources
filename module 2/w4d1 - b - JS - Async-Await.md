
# JS - Async/Await

<!--

- Status: just some notes

-->


- IMPORTANT NOTES on "Async" keyword: 
  - the async keyword transforms a function so that when the function is invoked, the return value will be wrapped in a Promise
  - The return value of an async function is always wrapped in a Promise. Put in other words, async function always returns a Promise.


- Syntax: function statement & arrow function expression

  ```
  async function doSomething() {
    //do something
  }
  ```

  ```
  const foo = async () => {
    // do something
  }
  ```

- Error handling:

  ```
  async function getInfoFromDB() {
    try {
      await doSomething(0);
      await doSomething(1);
      await doSomething(2);    
      console.log("all worked well");
    } catch(err) {
      console.log(err)
    } 
  }
  ```


