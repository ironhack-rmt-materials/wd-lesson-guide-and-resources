
# CSS - Responsive Web Design

<!--- Status: complete --->


## Intro


- What is responsive web design

- Dev-tools: show responsive mode + breakpoints

- Mobile-first: 
  https://www.initcoms.com/wp-content/uploads/2017/04/14955251486_67b5880508_c-e1493291308968.jpg

- Same html + different css rules



## Media queries

- Apply CSS rules only for devices that match specific characteristics (e.g. screen size)

- Syntax:

    ```html
    <link rel="stylesheet" media="(media-features)" href="styles.css" />
    ```

    ```css
    @media [(media-features) ] {
    // Styles
    }
    ```


- Show live example: https://codepen.io/ironhack/pen/ozZbmP

  <!-- @LT: show example on the code from yesterday -->

    ```css
    @media (min-width: 800px) {
    .responsive-div {
        background-color: blue;
    }
    }
    ```


- Explain Concept of "breakpoint" (see on dev tools)
  - Common breakpoints (e.g. bootstrap)



- Multiple conditions:

    ```css
    @media (min-width: 650px) and (max-width: 999px) {
      .responsive-div {
          background-color: green;
      }
    }
    ```


- Note: 
  - media queries do not change the specificity of your selectors.

- Common approach:
  - mobile-first
  - media queries for bigger screen later in the code



## Practice: Responsive layout (2 boxes, mobile first)

Before we start, 
- see the initial code
  <!-- Remember to FORK -->
- see that boxes are displayed one after the other (why: divs are block elements)
- How we can have them in the same line:
  - One option is to use `display: inline-block`
  - https://www.w3schools.com/cssref/pr_class_display.asp
- Also: explain how they can test different screen sizes on Codepen


Instructions:
- Initial code: https://codepen.io/luisjunco/pen/yLvZYLO
- Task: when screen is bigger than 600px, display the boxes in a row & change background color
- Expected result (demo): https://codepen.io/luisjunco/full/yLzwodK
- Bonus 1: add multiple breakpoints
- Bonus 2: explore other things (e.g. rounded corners, shadows, etc)

- Time: 10-15m


Solution: https://codepen.io/luisjunco/pen/yLzwodK
Preview: https://codepen.io/luisjunco/full/yLzwodK



## Viewport metatag

- Goes in the HTML head
- Gives the browser instructions on how to control the page's dimensions and scaling.


> A typical mobile-optimized site contains something like the following:


    ```html
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    ```


Why:
- watch this video (from 0:00 to 2:00): https://www.youtube.com/watch?v=SElOdK2qTpI
- see how viewport metatag was added to the code we produced yesterday




## (skip) Responsive Font Size

- Intro A. Recommendations from usability experts:
  - font-size of at least 16px
  - less than 20 words per line
  - ~ 1.4 line-height

- Intro B. CSS units (Absolute vs Relative)
  - Absolute: fixed (px, cm, mm...)
  - Relative: they're relative to another length property. Scale better between different rendering mediums (%, em, rem, vw).

  <!-- @LT: explain each of those units. -->


- Option 1 (skip): using Viewport Units

  - e.g. font-size: 1vw
  - problem: text can easily get too big or too small (tip: calc(10px + 1vw) )


- Option 2: root font-size in pixels + relative units & media queries

  - example: https://codepen.io/luisjunco/pen/QWaaGwq

  - Advantage: css usually easier to maintain

  - Alternative - The 62.5% Font Size Trick: https://www.aleksandrhovhannisyan.com/blog/62-5-percent-font-size-trick/#example-a-user-prefers-larger-font-sizes



