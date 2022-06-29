# LAB | DOM Ironhack Cart

[REPO](https://github.com/ironhack-labs/lab-dom-ironhack-cart)

[SOLUTION](https://gist.github.com/IH-WebDev-TA-Remote/c67a111bcc4b2ba521c5a7e28e2ecbaa)

### REMIND

- Fork
- Clone
- Actions

### Guidelines for LAB

Work in:
 - index.js (main file)
 - index.html

## NOTES @TA

 1. Show window event listener (bottom of the page)
 2. In calculateAll(). querySelector -> gets first found element
 3. When blue button clicked -> printed in console

## TIPS

- console.log element you are accessing
- be aware where/when are you console.logging

### ITERATIONS

Iteration 1: 

 - read value of price → .innerHTML
 - read value of quantity → .value
 - do the math
 - use it in another dom element 

Iteration 2 & 3: 

 - add another product in html file
 - find all product
 - maybe keep it in array? -> if using getElementsByClassName convert HTML Collection to array

Bonus 4 & 5:
- remove
- create  
<br>  
- TESTS
- similar logic to 'calculate prices'
- add event listener on window load 
    - listener for parentElm
    - removeChild
- event.currentTarget