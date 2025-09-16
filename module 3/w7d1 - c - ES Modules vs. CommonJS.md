
# ES Modules vs. CommonJS


<!-- @todo: 
  - create a diagram/image with code snippets comparing both
  - create a small exercise to practice
-->



## Intro: ESM vs. CommonJS

ES6 modules
- export
- import


Common JS
- module.exports = 
- require()


## Demo

<!-- @LT: show demo on node (locally) -->

- mkdir module3
- mkdir commonjs-demo
- cd commonjs-demo
- touch index.js
- touch utils.js


Example 1 (exporting a single value):

  ```js
  const amount = 42;

  module.exports = amount;
  ```


Example 2 (exporting multiple values in an object):

  ```js
  function calcTotal(a, b){
      return a * b;
  }

  function calcDivision(a, b){
      return a / b;
  }

  function calcAverage(a, b){
      return (a + b) / 2;
  }

  module.exports = { calcTotal, calcDivision, calcAverage, };
  ```


