
# LAB - JS Chronometer - OLD


Explain:
- all the functionality for the UI is given to us
- we need to implement the class Chronometer (logic)


Work only on `javascript/chronometer.js` and pass the tests.
The rest of the code is given to us and it is using our Chronometer class.



## Iteration 1: The Chronometer class

constructor:
- `currentTime`, with the initial value set to 0.
- `intervalId`, with the initial value set to null.


## Iteration 2: The start method


IMPORTANT:

- expects a callback (`printTimeCallback`). They'll need to check if it's provided: 

  ```js
    if(printTimeCallback){
      //...
    }
  ```


- every second (`setInterval`), we need to:
  - increases counter
  - invoke `printTimeCallback` (if it is a function, execute it)

- for the interval, use an Arrow Function for `this` binding (it is stated in the instructions)


## Iteration 3: The getMinutes method

## Iteration 4: The getSeconds method

## Iteration 5: The computeTwoDigitNumber method

## Iteration 6: The stop method

## Iteration 7: The reset method

## BONUS - Iteration 8: The split method

## BONUS - Iteration 9: Centiseconds



