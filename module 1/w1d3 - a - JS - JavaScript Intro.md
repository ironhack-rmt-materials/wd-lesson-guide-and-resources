

# JS - JavaScript Intro

<!--- 

Status: JUST SOME NOTES

@todo: make summary of topics

-->




## Comments



## What is a variable?

- what is a variable


## Declaring a variable

- declare vs. initialize

- If you don’t assign a value to a variable when you declare it, its default value will be initialized to undefined.



## Naming a variable



## Scope


```js

// Scope = where in the code we can access a variable
//
// - children have access to parent's scope
// - parent do not have access to child's scope

```


## var, let, const

Note: make sure we've explained SCOPE FIRST.


Const:
- const is used when declaring a variable which value will be constant (ie. we're not planning to reassign the variable).


Scope Differences:
- var: global/function scope
- let, const: global/block scope


Video:
- let vs. var vs. const - Mosh (7m): 
  https://www.youtube.com/watch?v=XgSjoHgy3Rk



## Type

- data types
- operator typeof



## First-Class functions

- In a variable, we can store any valid data type (number, string, array....)

- We can also store a function


```js
const sayHello = function () {
  console.log('hello world');
};

sayHello();
```


```js
/*

first-class functions = functions are treated like any other variable

- we can store a function in a variable
- we can pass a function as an argument to another function
- a function can return a function

*/
```