

# Extra - TypeScript


## Demo Option I:

Quick demo on stackblitz.


## Demo Option II:

- `npm i -g typescript`

- create `index.ts` & add `console.log()`

- `tsc index.ts`

- by default, it translates to ES3 (ex. let will be translated to var)

- add `tsconfig.json`:

    ```json
    {
        "compilerOptions": {
            "target": "ES2017",
            "watch": true, //listen for changes
        }
    }
    ```


- run with `tsc` (will listen for changes in current directory)

- 2 ways to define types: Implicit & Explicit

- Implicit types

    ```ts
    let amount = 20;
    amount = "fifty";
    ```

- Explicit types

    ```ts
    let amount1: number; //declaration
    let amount2: number = 20; //declaration + initialization (no need to add explicit type)

    amount1 = "50";
    amount2 = "60";
    ```


- Function arguments:

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


- Arrays:

    ```ts
    const numbers = [1, 2, 3]; //implicit
    const names: string[] = ["alice", "bob"]; //explicit

    numbers.push(4);
    // numbers.push("5"); //error

    names.push("charly");
    // names.push(false); //error
    ```


- (extra) Interfaces

    > Interfaces let you compose multiple type annotations into a single named annotation. 

    ```ts

    interface User {
        userName: string,
        age: number,
        favFood?: string, // ? --> optional
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


- (extra) array of interfaces

    ```ts
    interface User {
        userName: string,
        age: number
    }

    const user1: User = {
        userName: "alice",
        age: 20
    }

    const user2: User = {
        userName: "bob",
        age: 21
    }


    let usersArr: User[];

    usersArr.push(user1)
    usersArr.push(user2)
    // usersArr.push({foo: "bar"}); //error

    ```



## Learning Resources

Video: TypeScript - The Basics (12min.)
https://www.youtube.com/watch?v=ahCwqrYpIuM


Gitbook - TypeScript Deep Dive 
https://basarat.gitbook.io/typescript/


Codewars - Learning Typescript collection
https://www.codewars.com/collections/learning-typescript


React TypeScript Tutorial for Beginners (Codevolution)
https://www.youtube.com/playlist?list=PLC3y8-rFHvwi1AXijGTKM0BKtHzVC-LSK



## Further challenges

Challenge 1: learn how to create a to-do list in plain JS
  - Video - How To Build Your First TypeScript Project - TODO List Application (30min.): https://www.youtube.com/watch?v=jBmrduvKl5w


Challenge 2: learn how to create a to-do list with TS + React
  - Video - Todo List in ReactJS using TypeScript Tutorial (40min.): https://www.youtube.com/watch?v=bjnW2NLAofI


Challenge 3: 
- create a new project (similar to p3 but using TypeScript).
  


