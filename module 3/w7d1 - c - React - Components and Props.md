

# React - Components & Props


<!-- 

Status: just some notes as a summary 

Notes:
- Some students find it difficult to remember how to pass & receive props (even after a few days).


@todo: prepare a basic exercise to practice Components + props.
  - create stackblitz
  - ask students to create a child component
  - pass info from parent to child
  - (extra) create grandchild & pass info to grandchild
  - (this can also be a good exercise to warm-up tomorrow)

-->


Intro Slides (function vs class components): 
https://docs.google.com/presentation/d/1iqYSImZj7p58ahLWryMSp00ooCCEf2cnIhjwc-pMFqw/edit?usp=sharing

<!-- 
  @todo: 
  - add some code syntax to the slides (how to pass props when we render a component etc)
-->


## Function and Class Components

- Differences
- How to create a function component
- How to create a class component

Examples: 
- https://reactjs.org/docs/components-and-props.html#function-and-class-components


Example: create a sample app with the following components inside `<App />`:

- `<Header />`
- `<User />`
- `<Footer />`


Notes:
- Class component: we must import React in the file.
- Class component: must contain a render(){} method:


## Know how the Component tree works
-  component tree 


## Props


Intro example (why props):
- `<Header />`
- `<UserOne />`
- `<UserTwo />`
- `<UserThree />`
- `<Footer />`


<!-- 
  @Luis: 
  we can also start simple passing props to the header (ex. title).
-->



> Conceptually, components are like JavaScript functions. They accept arbitrary inputs (called props) and return React elements describing what should appear on the screen.

  - Example with functions (show how we can create a generic function using arguments): https://stackblitz.com/edit/js-5tsf94?file=index.js


- Passing and accessing a prop
- Passing multiple props


Exercise (OPTION 1) to practice the syntax:
- Ask students to delete User component (and the lines to render it in App.js)
- Task:
  - create User component (function component)
  - render User in App.js
  - using props, display Alice & Bob
  - (bonus): pass a second prop to display the fav food of each of them (ex. salad, pizza)
- (bonus): pass a third prop to display the age of each of them (hint: `age={20}`)
  - (bonus): pass an object as props (ex. an object with name and favFood)




Note: As props, we can pass any valid data type


## Practice: react props

<!-- same but with movies (instead of users) -->


  Initial code: 
  - https://stackblitz.com/edit/react-flgcfo?file=src/App.js
  -  note: in App.js we have an array of movies

  Iteration 1: 
    - create a component "Movie" (for this iteration, just display an h1 ex. `this is the Movie component`).
    - note: in stackblitz, you need to import react in each file:
      - `import React from 'react';`

  Iteration 2: 
    - in App.js, render 3 times the Movie component

  Iteration 3: 
  - use props to make the component generic
  - in app.js, you will need to send each element of the array as props.

  ```jsx
    <Movie details={moviesArray[0]} />
    <Movie details={moviesArray[1]} />
    <Movie details={moviesArray[2]} />
  ```

  Bonus: display in the Header the number of movies.
  Bonus: add some cool CSS.


  Time: 15min.


  Solution: https://stackblitz.com/edit/react-e2bf8p?file=src/components/Movie.js


---


- Todays lab:
  - They will be passing elements of an array:
    `<Tweet tweet={ tweetsArray[0] }>`
    `<Tweet tweet={ tweetsArray[1] }>`
    `<Tweet tweet={ tweetsArray[2] }>`
  - Each element is an object (ie. `props.tweet` is an object)



## (Introduce) How to iterate through a list

```jsx
  arr.map();
```



## Props and Data Types

- As props you can pass...
  - string, number, boolean, array, object, function... 
  - A JS expression (eg. foo={2+2})

- `props.children`


## props.children




## When do you use props?







## IMPORTANT: props are immutable

- props are immutable: you must never modify the `props` that a component receives.
  - https://reactjs.org/docs/components-and-props.html#props-are-read-only

  - (extra) explain the concept of a `pure function`
    > All React components must act like pure functions with respect to their props.




## (extra) Components from npm

- React Player:
`npm install react-player`

`<ReactPlayer url="https://vimeo.com/channels/top/22439234" playing />`

- (extra) Component Libraries
  - Show an example with one of them (eg. "Material UI"/ "Semantic UI React" / "Ant Design")
  - https://ant.design/components/button





## (extra) Receive props with object destructuring

  - Option1: 
    ```js
      function User(props) {

        const {name, surname} = props;

        //...
      }
    ```


  - Option2 (directly): 

  ```js
    function User({name, surname}) {
      //...
    }
  ```


