
# w4d1

<!--

Status: ready

Goal: 
- 15:00 start lab
  - advanced students: if they finsih, they can start this one: https://github.com/ironhack-labs/lab-js-es6-reinforcement

- 17:00: (bonus) explain how to create promises


-->




## Project feedback (ask TAs)

<!--

Project 1 feedback:

- pls check students projects and, for each project, do the following 2 things (you may need Monday + Tuesday):

1. Give feedback to students (ex. if you see anything to they can learn from).
- Let's keep it positive.
- Let's keep it brief (they'll be busy)
- Let's keep it focused on things they can learn from (they will probably not have time to implement any suggestions)

2. Grade each project.
- I believe we don't have specific guidelines for that grade, so let's take into account both code + final result.
- That grade can be done from the same person that reviews each project
- Let's also aim for simplicity (we should not spend more than 2-5 minutes to decide each mark :pray:).


-->





## Planning


- Intro to module 2 (see: `module 2\w4d1 - - Intro to  module 2.md`)



- (extra) explain object destructuring
  - @LTs: I do that as a warmup + gives us extra time in the following days.




- Refresh on Asynchronous code & callbacks
  - create functions `getInfoFromDB` and `displayInfo`
  - it takes some time to get info from DB. Once it's ready, we want to display it (callback).
  - Final result: https://stackblitz.com/edit/js-m92ra4?file=index.js



- Introduce .fetch(). 

  - Show this code (at the end of the day it should be much more clear):

    ```javascript
      fetch('https://jsonplaceholder.typicode.com/users')
      .then((response) => {
        return response.json();
      })
      .then((data) => {
        console.log(data);
      })
      .catch((error) => {
        console.log(error);
      });
    ```

  - Extra concepts:
    - API & REST API
    - JSON

  - See how .fetch() returns a Promise
  
    ```javascript
      const result = fetch('https://jsonplaceholder.typicode.com/users');
      console.log(result);
    ```


- Introduce the concept of Promises & explain why they were added to JS
  - Definition of promise from MDN
    > The Promise object represents the eventual completion (or failure) of an asynchronous operation and its resulting value.


- CONSUMING PROMISES with .then().catch()
  - follow planning in `w4d1 - a - JS - Promises.md` (starts with callback hell)


- CONSUMING PROMISES with async/await
  

- Make sure `.fetch()` is explained during the day


- LAB
  - show how the function obtainInstruction() returns a Promise


- (after lab) CREATING PROMISES



## Extra challenges

- Advanced users can do this lab (currently not in the schedule):
  - LAB JS ES6 Reinforcement (for...of loop, .filter()):
    https://github.com/ironhack-labs/lab-js-es6-reinforcement
  



