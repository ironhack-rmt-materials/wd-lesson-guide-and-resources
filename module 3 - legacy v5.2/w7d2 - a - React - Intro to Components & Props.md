
# React - Intro to Components & Props

<!-- Status: draft -->

## Intro:

- Refresh components

- Component hierarchy

- In this lesson we will learn:
  - How to create components
  - How to pass information to compoenents


- 2 types of components:
  - Function components
  - Class components

  https://reactjs.org/docs/components-and-props.html#function-and-class-components


## Create a function component

```
function Header() {
  return <h5>Hello World</h5>;
}
```


## Create a class component

```
class Header extends React.Component {
  render() {
    return <p>Welcome to our React App</p>
  }
}
```





## Function vs Class components (when to use each)






## Props

- Codealong: recipes web app (header, cards with recipes each with a title)

- Note: props are immutable (props are read-only)


- Advantages of props:
  - You can use props to make your components reusable. 
  - We can share data between components
    - Remember: data flows down



## props.children

>  any data can be passed to a component using props


```
function App() {
  return (
    <div>
      <h1>List of users...</h1>
      <UsersList>
        <User firstName="Harper" />
        <User firstName="Mike" />
        <User firstName="Alvaro" />
        <User firstName="Andrea" />
      </UsersList>
    </div>
  );
}
```

```
function UsersList(props) {
  return <div> {props.children} </div>;
}
```



## Check for understanding


## Components from npm

Examples: 
  - react-player
  - bulma (used in the lab)