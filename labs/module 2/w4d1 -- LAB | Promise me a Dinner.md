# LAB | Promise me a Dinner

[REPO](https://github.com/ironhack-labs/lab-es6-promises)

[SOLUTION](https://gist.github.com/TA-Remote/b072e1452f6aaa50853484c3d718fa81)

### REMIND

- fork
- clone

### Guidelines for LAB

In javascript folder
- data.js -> can check correct order there
- index.js (write code there)

ITERATION 1
- getInstructions.js  - a callback f do not edit (pay attention what is passed)
	- after you finish first step , you want to call another function for the 2nd step  


ITERATION 2 & 3
- obtainInstructions.js  - (pay attention what is passed)  


ITERATION 3
- here you are defining the function, so you need to call it as well

BONUS
- bonus1 include images
- promise.all


## TIPS

- don't think about making code smaller, the idea is to learn syntax for every method  and understand how it works

1. Syntax:
	- always write the structure only then fill it in with content
	- no semicolon after .then

2. If you want to use smth from the promise you NEED to receive it. Can always console.log the response
3. If you want to chain promises, you MUST return smth
4. Dom manipulation is not asynchronous, you can have several line in one promise
	- eg. If you want to change innerText and add new color attribute, don't need separate promises
5. With async/await in this case not essential to catch errors  

<br>

ADDITIONAL GOAL WHEN WORKING IN TEAM
- both understand.
- read task together
- not just quickly complete
- don't give solution - but explain to each other if not clear