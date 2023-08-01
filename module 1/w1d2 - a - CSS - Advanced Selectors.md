

# CSS Advanced Selectors



<!--

methodology: self-guided, just mention a few things

-->


Initial HTML code:
- https://stackblitz.com/edit/web-platform-pbyzia?file=index.html



## Multiple selection



```
selector1, selector2 {
    property: value;
}
```



## Descendant Selector

```
selector1 selector2 {
  property: value;
}

```


- Example when it can be very useful:

    ```
    <ul>
        <li class="menu-item"></li>
        <li class="menu-item"></li>
        <li class="menu-item"></li>
        <li class="menu-item"></li>
        <li class="menu-item"></li>
    </ul>
    ```

    ```
    .menu-item {
        width: 100px;
        height: 50px;
    }
    ```


## Ancestors vs descendants etc.


- An HTML document can be represented as a tree.
  - example: https://i.imgur.com/YdqDUNh.png



> A `parent` is an element that is directly above and connected to an element in the document tree

> A `child` is directly below and connected to an element in the document tree.


> in any HTML document, the <body> element is the `ancestor` of all other elements. 

> a `descendant` refers to any element that is connected but lower down the document tree - no matter how many levels lower.



## Direct Descendants (Children)



```
parent > child {
  property: value;
}
```



## Adjacent Sibling

```
formerElement + targetElement {
  property: value;
}
```

- separates two selectors and matches the second element only if it immediately follows the first element, and both are children of the same parent 


## Attribute Selector


```
element[attr-name='value'] {
    property: value;
}
```

- Target elements with the specified attribute

- Also allows to do things like "begins with", "contains", etc (see table on students portal)

Ex:
  ```css
  img[attribute$=kitten] {

  }
  ```



## Mixing things....

```
.todo-list > li,
h2 + .red-box,
h2 {
    background-color: yellow;
}
```


## (bonus) CSS custom properties (variables)

- Set using custom property notation
  - `--main-color: black;`
- Use with the var() function
  - `color: var(--main-color);`


  ```css

  :root {
    --main-color: orange;
  }

  body{
    color: var(--main-color);
  }

  .box {
    border: 2px solid var(--main-color);
  }

  ```




## Good practices

- Generic rules first
- Specific rules later