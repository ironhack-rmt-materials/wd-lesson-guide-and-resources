
# React - Conditional Rendering



## Conditional Rendering

- Intro: refresh ternary operator

- Explain:
  - Cheatsheet: https://gist.github.com/luisjunco/7eab10cd2991fab11a759add4a15b7cc

  <!-- @todo: add demos (stackbliz) to the cheatsheet (plus quick exercise) -->


- Examples:
  - `Element Variables` if there's zero movies, display a different message
  - `Logical && Operator`: if rating > 8 display a text "RECOMMENDED"
  - `Ternary Operator`: if imgURL not  available, display placeholder image
    - ex: https://dummyimage.com/182x268/ffffff/000000

  - (bonus) if rating > 8 apply a different background (hint: `className`)


      - (Extra) CSS for "RECOMMENDED":

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
  <!-- @Luis: skip this (we haven't seen comunication from child to parent component + they don't need it for today's lab) -->
  - this component will display the title of a movie.
  - From Main.js, render the Movie component (pass the title as props)



## (Extra challenges):
  - Implement a button "Show only top-rated"
    - When the user clicks, display only movies with rating > 8
  
  - Add button to sort by rating

  - Add favIcon
    - Can use these images: https://github.com/Ironhack-Team-Triangle-July2021/ironhack-cinema/commit/f4cf21c91608b1fdf95b359031e676c90cbf8c3f#diff-09e657b7706f48b0af84577d8d340912648fa2d247d808a18e26e3459df1a26b

  - Research: JSX spread attributes.
    - `<Movie {...movieObj}>`
      
