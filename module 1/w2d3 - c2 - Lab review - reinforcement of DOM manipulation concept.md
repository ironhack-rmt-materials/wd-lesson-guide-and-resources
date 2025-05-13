

# Lab review - reinforcement of DOM manipulation concept


<!--- 

Notes:
- complete up to iteration 3
- iterations 4 & 5: we usually don't have time to do it in class

-->


## Goals:
- Practice DOM manipulation
- Collaboration using Git


## Pre-Setup:
- Create organization on GitHub + add all members
- Fork lab (fork it on the Organization profile) -- Students will the clone it to collaborate.


## Iteration 0:

- Explain lab (what we're going to build)
- Go through initial code (html, initial js)
- Run tests


## Iteration 1: updateSubtotal()

- get reference to the elements of the dom that hold price & quantity
- get the value for price: elm.innerText + parseFloat
- get the value for quantity: elm.value + parseInt

- calc subtotal (priceValue * quantityValue)

- update the dom to display subtotal

- return subtotal (e.g. `return subtotalValue;`)
  - this is important so that we can use it later to calc the total price


## Iteration 2: calculateAll()

- intro:
  - what we need to do
  - steps we will follow

- Step 0: 
  - remove the existing code in calculateAll() (this code was just for iteration1)
  - add a new product (duplicate a row in index.html)

- Step 1: get a list with all the products (elements of the dom)

```
document.getElementsByClassName('product'); // returns an html collection
document.querySelectorAll('.product'); // returns a Node List
```

- Step 2: iterate through this list (might need to convert to an array, in case it's an html collection)

- Step 3: for each iteration, call updateSubtotal(product) -- this will update the dom with the subtotal for each product



## Iteration 3: calc & display total

- calculate & display the total price
  - e.g. initialize a variable totalValue=0 and update for each iteration



## (Bonus) Iteration 4: functionality to remove products


## (Bonus) Iteration 5: functionality to add new products


