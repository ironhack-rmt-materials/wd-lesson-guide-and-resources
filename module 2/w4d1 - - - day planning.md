
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


<!--
@Luis

- ADAPTABLE -- ask students to signup for BETA
  - https://adaptable.io/app/signin

-->



- (extra) object destructuring
  - @LTs: I do that as a warmup + gives us extra time in the following days.



- Introduce concepts:
  - API & REST API
  - JSON




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


  - See how .fetch() returns a Promise
  
    ```javascript
      const result = fetch('https://jsonplaceholder.typicode.com/users');
      console.log(result);
    ```







- CONSUMING PROMISES with async/await
  

- Make sure `.fetch()` is explained during the day





## Extra challenges

- Advanced users can do this lab (currently not in the schedule):
  - LAB JS ES6 Reinforcement (for...of loop, .filter()):
    https://github.com/ironhack-labs/lab-js-es6-reinforcement
  



