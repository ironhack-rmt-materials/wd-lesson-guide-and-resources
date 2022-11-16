

# React - Components & Props


<!-- 

Status: just some notes as a summary 

Notes:
- Some students find it difficult to remember how to pass & receive props (even after a few days).

- Do more practice with a basic exercise. Ex: 
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
  - (bonus): pass an object as props (ex. an object with name and favFood)



Exercise (OPTION 2) same but with movies (instead of users)

  ```javascript
    const moviesArray = [
      {
        title: 'the godfather',
        rating: 9,
      },
      {
        title: 'Pulp Fiction',
        rating: 8,
      },
      {
        title: 'Coco',
        rating: 9,
      },
    ];
  ```
    
  - create a component Movie
  - render 3 Movie in App.js

  - use props to make the component generic
  - in app.js, you will need to send each element of the array as props.

  ```jsx
    <Movie details={moviesArray[1]} />
  ```






- Todays lab:
  - They will be passing elements of an array:
    `<Tweet tweet={ tweetsArray[0] }>`
    `<Tweet tweet={ tweetsArray[1] }>`
    `<Tweet tweet={ tweetsArray[2] }>`
  - Each element is an object (ie. `props.tweet` is an object)



## props.children



## When do you use props?



## Components from npm

- React Player:
`npm install react-player`

`<ReactPlayer url="https://vimeo.com/channels/top/22439234" playing />`

- (extra) Component Libraries
  - Show an example with one of them (eg. "Material UI" or "Semantic UI React")



## Extra Concepts

- As props you can pass...
  - string, number, boolean, array, object, function... 
  - A JS expression (eg. foo={2+2})


- (Extra) Props defaults to true

  ```jsx
  <MyTextBox autocomplete />
  <MyTextBox autocomplete={true} />
  ```


- props.children


## IMPORTANT CONCEPTS

- props are immutable: you must never modify the `props` that a component receives.
  - https://reactjs.org/docs/components-and-props.html#props-are-read-only

  - (extra) explain the concept of a `pure function`
    > All React components must act like pure functions with respect to their props.

