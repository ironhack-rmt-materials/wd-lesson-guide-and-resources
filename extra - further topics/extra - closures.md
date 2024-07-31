

# Extra - closures





## Example 1


```js

function makeCounter() {
  let counter = 0;

  return function () {
    counter++;
    console.log(counter);
  };
}

const increase = makeCounter();

increase();
increase();
increase();

// console.log(counter); // Error: counter is not defined

```






## Example 2


```js
function multiplierFactory(factor) {
  return function (number) {
    return number * factor;
  };
}

const double = multiplierFactory(2);
const triple = multiplierFactory(3);

console.log(double(5)); // Output: 10
console.log(triple(5)); // Output: 15
```