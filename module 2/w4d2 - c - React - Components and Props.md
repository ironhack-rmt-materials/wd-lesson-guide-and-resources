

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


Intro Slides (conponents + function vs. class components): 
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


For User:
```jsx
  function User(){
      return(
        <h1>Name: Alice</h1>
      );
  }
```




## Know how the Component tree works
-  component tree 




## Props I (syntax)

- Intro to props & syntax:
  - passing props to the `Header` (ex. title).


## Explain: props are similar to function arguments 

> Conceptually, components are like JavaScript functions. They accept arbitrary inputs (called props) and return React elements describing what should appear on the screen.

Example with functions (show how we can create a generic function using arguments): https://stackblitz.com/edit/js-5tsf94?file=index.js


## Props II (using props to make our components more reusable)

- Second example (why props are useful)

  ```jsx
  function User(){
      return <h1>Name: Alice</h1>;
  }

  export default UserOne;
  ```


- `<Header />`
- `<UserOne />`
- `<UserTwo />`
- `<UserThree />`
- `<Footer />`



- Passing and accessing a prop
- Passing multiple props
  - Note: we could also pass an object (ex. `userDetails={}`)



Note: As props, we can pass any valid data type



## Practice: components and props

Initial code: 
- https://stackblitz.com/edit/react-flgcfo?file=src/App.js
-  note: in App.js we have an array of movies

Iteration 1: 
  - create a component "Movie" (for this iteration, just display an h1 ex. `this is the Movie component`).
  - IMPORTANT: in stackblitz, you need to import react in each file (`import React from 'react';`)

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

Bonus 1: display in the Header the number of movies.

Bonus 2: Keep challenging yourself further. 
- For example, add some cool CSS & make it look like this: https://freefrontend.com/assets/img/css-card-layouts/CSS-Responsive-Cards.jpg


Time: 20min.


Solution: https://stackblitz.com/edit/react-e2bf8p?file=src/components/Movie.js



---

Note: Todays lab

- They will be passing elements of an array:
    `<Tweet tweet={ tweetsArray[0] }>`
    `<Tweet tweet={ tweetsArray[1] }>`
    `<Tweet tweet={ tweetsArray[2] }>`
- Each element is an object (ie. `props.tweet` is an object)



Mention: 
- we will see options to iterate through an array.
- for now, they can use the syntax we've seen so far.




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





## (skip for now) Receive props with object destructuring

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


