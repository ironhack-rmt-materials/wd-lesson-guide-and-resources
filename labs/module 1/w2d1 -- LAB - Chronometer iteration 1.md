# LAB | Chronometer iteration 1

[REPO](https://github.com/ironhack-labs/lab-javascript-chronometer)

[SOLUTION IT 1](https://gist.github.com/TA-Remote/8b37a470f179c7e94e6327acacabcf04) 

[LATEST SOLUTION](https://gist.github.com/TA-Remote/d39dc2fe1eae6c36115d936c9f655b16)

### REMIND

- Fork
- Clone

### Guidelines for LAB

- tests 
- only logic in iteration 1
- work in chronometer.js file 
<br>

<br>  
WHEN YOU OPEN FILE  

- Chronometer class + methods
- keyword this.

- inside setInterval:
    - @TA: say what will happen. The setInterval() method, repeatedly calls a function or executes a code snippet, with a fixed time delay between each call.  
    - @TA: use arrow functions to keep the `this` to the context of the chronometer, otherwise it'll reference the global object
      <br>  
	 1. setInterval(function() => {}, 1000)
	 2. this.intervalId = setInterval(function()=>{}, 1000)
	 3. clearInterval(this.intervalId)

TRICKY PART  

If callback is passed it will be executed.

```
start(callback, time) {
    // here check if callback is passed or not. If it is passed - execute it
}
```	

- use arrow functions only!

    
- currentTime is saved in seconds (or 1000 milliseconds)
    - convert and return minutes
    - return seconds

- split()
    - use method: computeTwoDigitNumber(value)

