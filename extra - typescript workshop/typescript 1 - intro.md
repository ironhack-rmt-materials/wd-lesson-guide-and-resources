

# TypeScript intro



TypeScript in 100 Seconds (Fireship.io, 2min):
https://www.youtube.com/watch?v=zQnBQ4tB3ZA




## Intro: what is typescript

- Quick demo:

  <!-- @LT: create TypeScript project in Stackblitz -->

    ```js
    function calcTotal(a, b) {
        return a + b;
    }

    const result = calcTotal(5, '10');

    console.log(result);

    ```

## Intro: why TypeScript

- Advantages:
    - Type safety (early errors during development vs. run-time errors)
    - Can speed up development (sometimes...)
- Very common in the industry + job opportunities



## Initial Setup

- `npm i -g typescript`

- `tsc --version`

- `mkdir typescript-demo`

- `cd typescript-demo`

- `touch index.ts`

- `code -r .`

- add `console.log()`

- Run file: `tsc index.ts`

- by default, it translates to ES3 (ex. let will be translated to var)

- add `tsconfig.json`:

    ```json
    {
        "compilerOptions": {
            "target": "ES5", //compile to ES5, to ensure compatibility for old browsers
        }
    }
    ```


- run with `tsc --watch` (will listen for changes in current directory)

- note: 
    - typescript is a superset of JavaScript
    - you can write plain JavaScript code in TypeScript files, and it will still work.


## String, Numbers and Booleans

```ts
let userName: string = "alice";
let age: number = 30;
let isLoggedIn: boolean = false;
```


## Implicit vs. explicit types

- Implicit types

    ```ts
    let amount = 10;
    amount = "20";
    ```

- Explicit types

    ```ts
    let amount1: number; //declaration
    let amount2: number = 20; //declaration + initialization (no need to add explicit type)

    amount1 = "50";
    amount2 = "60";
    ```

## Unions

- Union types allow you to define a variable that can hold one of several specific types.

    ```ts
    let statusCode: number | string;

    statusCode = 200;
    statusCode = "not found";
    statusCode = true; // Error: Type 'boolean' is not assignable to type 'string | number'.
    ```

## (skip) Any

- any can be convenient in some cases but it also comes at the cost of losing type safety (which is one of the main motivations for using TypeScript).


## Functions

- Function parameters:

    ```ts
    function calcTotal(a:number, b:number) {
        console.log(a + b)
    }

    calcTotal(2, 3);
    ```


- Function returns:

    ```ts
    function calcTotal(a, b):number {
        return a + b;
    }

    calcTotal(2, 3);
    ```


## Arrays:

    ```ts
    const numbers = [1, 2, 3]; //implicit
    const names: string[] = ["alice", "bob"]; //explicit

    numbers.push(4);
    // numbers.push("5"); //error

    names.push("charly");
    // names.push(false); //error
    ```


## Type alias

- The keyword type (aka. type alias), provides a simple way to reuse type declarations.


Example 1: Player

    ```ts
    type Player = { 
        name: string, 
        year: number, 
        favouriteDrink?: string
    };

    const player1: Player = { name: "cristiano", year: 1985};
    const player2: Player = { name: "lionel", year: 1987, favouriteDrink: "mate"};
    ```

Example 2: User

    ```ts

    type User = {
        userName: string,
        age: number,
        likesPizza?: boolean, // ? --> optional
    }

    let user1: User;
    let user2: User;
    let user3: User;

    user1 = {
        userName: "alice",
        age: 20
    }

    user2 = {
        userName: "bob",
        age: "20" //error: Type 'string' is not assignable to type 'number'.
    }

    user3 = {
        userName: "bob", //error: Property 'age' is missing
    }

    ```


Example 3: array of users:

    ```ts
    type User = {
        userName: string,
        age: number,
        likesPizza?: boolean, // ? --> optional
    }


    let usersArr: User[];

    usersArr = [
        {userName: "alice", age: 30, likesPizza: true},
        {userName: "bob", age: 40},
        {userName: "charly", age: 50},
    ];

    ```



## Learning Resources


TypeScript Playground
https://www.typescriptlang.org/play

Video: TypeScript - The Basics (Fireship, 12min.)
https://www.youtube.com/watch?v=ahCwqrYpIuM


Gitbook - TypeScript Deep Dive 
https://basarat.gitbook.io/typescript/


Codewars - Learning Typescript collection
https://www.codewars.com/collections/learning-typescript


React + TypeScript Tutorial for Beginners (Codevolution, playlist ~2h)
https://www.youtube.com/playlist?list=PLC3y8-rFHvwi1AXijGTKM0BKtHzVC-LSK



## Further challenges

Challenge 1: learn how to create a to-do list in plain JS
  - Video - How To Build Your First TypeScript Project - TODO List Application (30min.): https://www.youtube.com/watch?v=jBmrduvKl5w


Challenge 2: learn how to create a to-do list with TS + React
  - Video - Todo List in ReactJS using TypeScript Tutorial (40min.): https://www.youtube.com/watch?v=bjnW2NLAofI


Challenge 3: 
- create a new project (similar to p3 but using TypeScript).
  


