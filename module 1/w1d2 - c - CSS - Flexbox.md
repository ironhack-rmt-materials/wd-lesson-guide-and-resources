
# CSS - Flexbox

<!--- 

Status: complete 


Approach:
- can show flexbox properties on dev tools & be changing them on the fly




Initial code:
  - remember to fork
  - remember to fork
  - https://codepen.io/luisjunco/pen/rNppeBZ
  - remember to fork
  - remember to fork


--->


<!-- 

@todo: create slides

-->


## Intro

<!--

- Example layout:
  https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/8d374c1e-228a-47e8-be5b-10fa1f4d40c8/mrh-css-grid-fig-01-large-opt.png

- Old website:
  https://i0.wp.com/css-tricks.com/wp-content/uploads/2017/10/screengrab_css-MacOS81.png?ssl=1

-->

- Evolution of CSS layouts: 
  - tables (still used in email)
  - floats
  - css frameworks (Bootstrap)
  - flexbox
  - grid.


- CSS support: https://caniuse.com

- Flexible Box Module (aka. "Flexbox")

- Flexbox: one dimension (deals with layout in one dimension at a time, either as a row or as a column)


- Flexbox vs. Grid: 
  - https://res.cloudinary.com/dukp6c7f7/image/upload/f_auto,fl_lossy,q_auto/s3-ghost//2019/09/Flexbox-vs-CSS-Grid.jpg


- Disclaimer (flexbox): we're going to see a lot of properties and concepts 


## The 2 axes of flexbox

- main axis + cross axis
  - diagrams: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox#the_main_axis

- main axis is defined by `flex-direction`

- possible values:

    ```
    flex-direction: row | row-reverse | column | column-reverse
    ```


## Flexbox Terminology


- Diagrams:
  - https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox/flex_terms.png
    - Relevant: 
      - Flex container
      - Flex item
      - Main axis
      - Cross axis


- Flex Container vs Flex Item



## Learn + practice with each property

How:
- Follow the guide at CSS Tricks while practicing with each property.
- We can also see/change in chrome dev tools


Links:

- CSS Tricks' guide: 
  - https://css-tricks.com/snippets/css/a-guide-to-flexbox/

- Joshw Comeau - Interactive Guide:
  - https://www.joshwcomeau.com/css/interactive-guide-to-flexbox/


- Playground initial code (remember to fork): 
  <!-- @Luis: remember to fooooooork !!  -->
  https://codepen.io/luisjunco/pen/rNppeBZ
  <!-- @Luis: remember to fooooooork !!  -->
  

<!--

.pizza {
  display: flex;
  justify-content: end;
}

https://img.ifunny.co/images/3257a1c9654c350aacc2d56069cc6d4a881349e0638dd27cd76fb1a082cb18f7_1.jpg

-->


## Practice: FlexBox

Responsive Navigation Menu:
  - Replicate this layout (note, it is responsive): https://codepen.io/team/css-tricks/full/YqaKYR
  - Note to students: 
    - focus on the distrubution of the elements (main goal is to practice flexbox; do not worry about details of the design, colors etc)
    - to simplify: we can target mobile + desktop only (1 breakpoint)
  - Time: 20-30min.
  - Solution (mobile first): https://codepen.io/luisjunco/pen/gOdPERa


Bonus:

- Implement this design (responsive):
  - https://codepen.io/chriscoyier/full/vWEMWw

- This CodePen includes some common patterns. Pick some of them and try to implement it with flexbox: https://codepen.io/paulobrien/pen/xVNMRZ



<!--

@todo:
- prepare an exercise similar to today's lab (or flexbox inside flexbox)

-->



## Flexbox Resources


** Guides and cheatsheets **

• A Complete Guide to Flexbox (CSS Tricks):  https://css-tricks.com/snippets/css/a-guide-to-flexbox/

• Interactive Guide (Joshw Comeau): https://www.joshwcomeau.com/css/interactive-guide-to-flexbox/



** Visual Cheatsheets **
• https://flexbox.malven.co/
• https://codepen.io/ironhack/pen/RLZXZR



** Practice **
• Flexbox Froggy: https://flexboxfroggy.com/
• Flexbox Defense: http://www.flexboxdefense.com/
• Guided tutorial at FreeCodeCamp: https://www.freecodecamp.org/learn/responsive-web-design/#css-flexbox


