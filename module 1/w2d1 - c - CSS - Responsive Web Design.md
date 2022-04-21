
# CSS - Responsive Web Design

<!--- Status: complete --->


## Intro


- What is responsive web design

- Dev-tools: show responsive mode + breakpoints

- Mobile-first: 
  https://www.initcoms.com/wp-content/uploads/2017/04/14955251486_67b5880508_c-e1493291308968.jpg

  https://i1.wp.com/css-tricks.com/wp-content/uploads/2021/02/pasted-image-0.png?resize=549%2C240&ssl=1



## Media queries

- Apply CSS rules only for devices that match specific characteristics (eg. screen size)

- Syntax:

    ```
    <link rel="stylesheet" media="(media-features)" href="styles.css" />
    ```

    ```
    @media [(media-features) ] {
    // Styles
    }
    ```


- Show live example: https://codepen.io/ironhack/pen/ozZbmP

    ```
    @media (min-width: 1000px) {
    .responsive-div {
        background-color: blue;
    }
    }
    ```


- Multiple conditions:

    ```
    @media (min-width: 650px) and (max-width: 999px) {
    .responsive-div {
        background-color: green;
    }
    }
    ```

- Note:  media queries do not change the specificity of your selectors.
  - Common approach:
    - mobile-first
    - media queries for bigger screen later in the code


## Viewport metatag

- Goes in the HTML head
- Gives the browser instructions on how to control the page's dimensions and scaling.


> A typical mobile-optimized site contains something like the following:


    ```
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    ```


## Exercise:

Task:
- Responsive layout (2 boxes, mobile first)
- Demo: https://codepen.io/luisjunco/pen/yLzwodK

- Explain / Refresh: display property
  - block, inline-block
  - https://www.w3schools.com/cssref/pr_class_display.asp

- Bonus: add multiple breakpoints

- Time: 10-15m ?



## Responsive Font Size

- Intro A --> Recommendations from usability experts:
  - font-size of at least 16px
  - less than 20 words per line
  - ~ 1.4 line-height

- Intro B --> CSS units (Absolute vs Relative)
  - Absolute: fixed (px, cm, mm...)
  - Relative: they're relative to another length property. Scale better between different rendering mediums (%, em, rem, vw).

--> explain each of those units.


- Option 1 (skip): using Viewport Units

  - eg. font-size: 1vw
  - problem: text can easily get too big or too small (tip: calc(10px + 1vw) )


- Option 2: root font-size in pixels + relative units & media queries

  - example: https://codepen.io/luisjunco/pen/QWaaGwq

  - Advantage: css usually easier to maintain



