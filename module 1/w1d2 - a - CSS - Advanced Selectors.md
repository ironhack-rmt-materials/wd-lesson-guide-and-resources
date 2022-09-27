

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



- Begins with, contains, etc --> see table on students portal



## Mixing things....

```
.todo-list > li,
h2 + .red-box,
h2 {
    background-color: yellow;
}
```


