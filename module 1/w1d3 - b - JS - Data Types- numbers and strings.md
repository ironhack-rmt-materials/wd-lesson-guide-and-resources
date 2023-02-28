
# JS - Data Types - numbers and strings

<!--- 

@Luis: follow students portal (highlighted)

Status: just some notes

-->



## Numbers

- represent integers and floating-point numbers in JavaScript

```js
const age = 34; //integer
const price = 12.99; //decimal
```



## NaN

<!-- 

@Luis: stackblitz doesn't work properly with NaN (UPDATE: seems to work now)

-->


```js
const result = 10 / 'pizza';
console.log(result);
```




## Modulo
- Modulo (%) is the remainder operator. 
<!-- - ex. 10 % 2 pizzas -->

Example:


  ```js
  const cakes = 5;
  const kids = 2;

  const remainder = 12 % 5;
  // console.log(remainder);
  ```




Demo (together):
- display numbers 1 to 12
- if number is odd, display `x is odd`
- if number is even, display `x is even`

  ```js
  for (let i = 1; i <= 12; i++) {
    // console.log(i);
    if (i % 2 === 0) {
      console.log(i, 'is even');
    } else {
      console.log(i, 'is odd');
    }
  }
  ```


Practice: FizzBuzz
  - how: individual / small teams (2-3 people)
  - time: 20-25m + solve together
  - https://stackblitz.com/edit/js-fizbuzz-exercise-p4hr4j?file=index.js

  - Solution: https://stackblitz.com/edit/js-fizbuzz-exercise-a6bphh?file=index.js



<!--

Fizz-Buzz
- it is in prework ("JS | Loops and iterations")
- another option is to do this kata together: 
  - https://www.codewars.com/kata/5300901726d12b80e8000498
  - Note: a bit challenging for day3 (solve TOGETHER).
  - Concepts: loop + arrays + modulo operator

-->


## Assignment Operators

Assignment: =	x = y
Addition assignment: +=
...


## Expressions




## Numbers:

> Operator Precedence: `4 * ( 5 - 2 ) + (2 + 2 ** 3) - 24 / 2`






## Strings


Creating a String
- "" double quotes,
- '' single quotes or
- `` backticks (grave accents).

  ```js
  const user1 = 'alice';
  const user2 = "bob";
  const user3 = `charly`; // ES6
  ```


Template literals:
- multiple lines
- interpolation

Ex:

  ```js
  const title = 'TLOTR';

  //string concatenation (old way)
  const msg1 = 'my favourite book is ' + title + ' and i love it';

  //Template Literals / String Interpolation
  const msg2 = `my favourite 
                book is ${title} 
                and i love it`;
  ```



Some topics: 
<!-- @todo: not comprehensive -->
> find out length of a string (str.length)
> concatenate 2 strings 
> get character at position N
> check if string contains a substring (indexOf() / includes() )
> get a substring of a string


  ```js
  console.log(msg2);
  console.log(msg2.length);
  console.log(msg2.charAt(1));
  console.log(msg2[1]);

  console.log(msg2.indexOf('m')); //0
  console.log(msg2.indexOf('w')); //-1 --> character does not exist
  console.log(msg2.indexOf('favourite')); //3
  ```




## Slice

  ```js
  slice(beginIndex)
  slice(beginIndex, endIndex)
  ```


Practice: strings & string methods: 
- Instructions: https://stackblitz.com/edit/js-1am8e2?file=index.js
- Time: 15-20min.
- Solution: https://stackblitz.com/edit/js-tsenus?file=index.js





## Sorting strings - .localeCompare()

<!-- 

they need it for today's lab 

-->



  ```js
  const user1 = 'bob';
  const user2 = 'charly';

  const result = user1.localeCompare(user2);
  console.log(result); // -1
  ```


```js
//
// str.localeCompare()
//

// -1 --> if the main string goes before the other one
// 0 --> same strings
// 1  --> if the main string goes after the other one
```