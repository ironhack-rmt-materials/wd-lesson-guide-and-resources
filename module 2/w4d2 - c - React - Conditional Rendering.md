
# React - Conditional Rendering


<!--

@todo: Record video

- initial code for video: https://codesandbox.io/s/cool-smoke-t68mxc?file=/src/App.js

- recording:
  - explain initial code
  - why we can not use if-else statement
  - intro cheatsheet + 3 ways
  - (bonus) can also create another app to show that conditional rendering applies to other cases, not just props (eg. when a counter of likes reaches a number - state)
  
-->



## Conditional Rendering

- Intro: refresh ternary operator

- Explain:
  - Cheatsheet (React conditional rendering): https://gist.github.com/luisjunco/7eab10cd2991fab11a759add4a15b7cc

  <!-- @todo: add demos (stackblitz) to the cheatsheet (plus quick exercise) -->


- Examples:
  - `Element Variables` if there's zero movies, display a different message
  - `Logical && Operator`: if rating > 8 display a text "RECOMMENDED"
  - `Ternary Operator`: if imgURL not  available, display placeholder image
    - ex: https://dummyimage.com/182x268/ffffff/000000

  - (bonus) if rating > 8 apply a different background (hint: `className`)


  - (extra) CSS for "RECOMMENDED":

      ```css
      .Main .badge {
        background-color: rgb(4, 128, 0);
        color: #fff;
        border-radius: 0.5rem;
        max-width: 200px;
        margin: 1rem auto;
        padding: 0.2rem;
      }
      ```



## (skip) Instead of a div, create a `<Movie />` component
  <!-- @LT: skip this (we haven't seen communication from child to parent component + they don't need it for today's lab) -->
  

