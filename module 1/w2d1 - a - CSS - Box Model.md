

# CSS - Box Model

<!--- Status: complete --->


## Intro 


- Every HTML element is a rectangular box

- Box-Model: https://i.imgur.com/LF204FU.gif

- Dev Tools: show box model


## Codealong

Follow the lesson starting from this simple code: https://codepen.io/luisjunco/pen/yLppaYV



## Border:


- Width, style, color:

```
    border-color: #17212e;
    border-style: solid;
    border-width: 1px;
```

- Shorthand:
    ```
    border: 1px solid #17212e;
    ```

- Spacing behavior: after adding the border, the element "uses" more space.

- Single borders

    ```
    border-bottom: 1px solid #17212e;
    ```


## Border-Radius

```
border-radius: 12px;
```


- Circle:

    ```
    .circular-div {
        background-color: #ccc;
        border-radius: 50%;
        height: 100px;
        width: 100px;
    }
    ```

## Padding

> Padding creates extra space within an element.

- Padding = space between the content and the border of an element

    ```
    padding: 10px;
    ```

- Other examples:

    ```
    padding: 10px 20px 30px 40px;
    ```

- Spacing behavior: after adding padding, the element "uses" more space.


- Units:
  - Absolute (px)
  - Relative (%, em, vw....)

- Possible values (4, 3, 2, 1):
  - https://learnwebcode.com/images/lessons/css-shorthand-1.gif
  - https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/0eb754a6-893b-4a48-b8d4-b9b2db0ee650/figurea.gif



## Box-sizing Property

- By default: when we add border/padding, the element "uses" more space.

- Sometimes, we have to fit the elements in a design.

- example:

    ```
    box-sizing: border-box;
    ```

- possible values:

  - content-box: default value. Width and height are calculated taking into account only the content (but not the padding and border).
  - border-box: width and height include the content, the padding and the border.




## Margin

- space between the border of an element and the other elements around it.

    ```
    margin: 10px 10px 10px 10px;
    ```


## Exercise

Students portal > Time to practice:
> Lorem Ipsum is a website where you can generate random content [...]





