
# CSS - Responsive Web Design

<!--- Status: complete --->


## Intro


- What is responsive web design

- Dev-tools: show responsive mode + breakpoints

- Mobile-first: 
  https://www.initcoms.com/wp-content/uploads/2017/04/14955251486_67b5880508_c-e1493291308968.jpg

  https://i1.wp.com/css-tricks.com/wp-content/uploads/2021/02/pasted-image-0.png?resize=549%2C240&ssl=1

- Same html + different css rules



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


- Explain Concept of "breakpoint" (see on dev tools)
  - Common breakpoints (ex. bootstrap)


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


## Exercise: Responsive layout (2 boxes, mobile first)

Before we start, 
- see the initial code
- see that boxes are displayed one after the other (why: divs are block elements)
- How we can have them in the same line:
  - One option is to use `display: inline-block`
  - https://www.w3schools.com/cssref/pr_class_display.asp
- Also: explain how they can test different screen sizes on Codepen


Instructions:
- Initial code: https://codepen.io/luisjunco/pen/yLvZYLO
- Task: when screen is bigger than 600px, display the boxes in a row & change background color
- Expected result (demo): https://codepen.io/luisjunco/full/yLzwodK
- Bonus: add multiple breakpoints

- Time: 10-15m


Solution: https://codepen.io/luisjunco/pen/yLzwodK



## Viewport metatag

- Goes in the HTML head
- Gives the browser instructions on how to control the page's dimensions and scaling.


> A typical mobile-optimized site contains something like the following:


    ```
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    ```



## Responsive Font Size (bonus)

- Intro A. Recommendations from usability experts:
  - font-size of at least 16px
  - less than 20 words per line
  - ~ 1.4 line-height

- Intro B. CSS units (Absolute vs Relative)
  - Absolute: fixed (px, cm, mm...)
  - Relative: they're relative to another length property. Scale better between different rendering mediums (%, em, rem, vw).

  <!-- @LT: explain each of those units. -->


- Option 1 (skip): using Viewport Units

  - eg. font-size: 1vw
  - problem: text can easily get too big or too small (tip: calc(10px + 1vw) )


- Option 2: root font-size in pixels + relative units & media queries

  - example: https://codepen.io/luisjunco/pen/QWaaGwq

  - Advantage: css usually easier to maintain

  - Alternative - The 62.5% Font Size Trick: https://www.aleksandrhovhannisyan.com/blog/62-5-percent-font-size-trick/#example-a-user-prefers-larger-font-sizes



