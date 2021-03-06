

# CSS - Intro & Selectors

<!--- 
Status: draft
-->


<!--

Feedback from students:
- Too much information for only one lesson (specially for those who didn't cover this in the prework).
- Make sure to start explaining why CSS + why selectors are useful +  clear examples


Sample code:
- This is the code we ended up with in cohort sept2021: 
  - "./module 1/code-samples/w1d3 - b - CSS - Intro and Selectors/"

-->


## Intro

- disable CSS



## how to add css
  - inline: `style=""`
  - in the head tag: `<style>`
  - external file: `<link rel="stylesheet" href="style.css" />`

- Paths:
    - External url. eg: https://mykittens.com/bob.jpg

    - Absolute path. 
        eg: href="C:\Luis\pro\Ironhack\_playground\html-hello-world\css\main.css"
        eg: href="/images/bob.jpg"

    - Relative path. 
      - `href="./images/bob.jpg"` (current directory)
      - `href="../images/bob.jpg"` (one directory above in the hierarchy)



## Intro CSS Selectors
- what are they
- why they're important
- why keeping CSS tidy is important
  - example of CSS project: https://codepen.io/celincky/pen/zdqso



## CSS structure: 
  -- selector & declaration block


## Selectors:

- why they're useful + how typical CSS looks like.

- type selector: div, p, h1...

- class: `class=""`
    - CONVENTION: underscore-with-dashes (kebab-case)
    - Can assign more than one class to an element (but do not add multiple times the class attribute: class="" class="") 


- id: `id=""`
  - CONVENTION: underscore-with-dashes
  - Each page can have only one element with that ID
  - Each element can have only one ID


- Universal selector
  - Warning: Be very careful when using the universal selector


- Combine selectors (only mention it, we will go in detail later)



- Cascade 
  - "the order of CSS rules matters; when two rules apply that have equal specificity, the one that comes last in the CSS is the one that will be used."
  - http://www.standardista.com/wp-content/uploads/2012/01/specificity3.pdf

- Specificity (Selector precedence)

- Inheritance
  - some CSS property values set on parent elements are inherited by their child elements (ex. `font-family`)
  - some aren't (ex. `width`)
  - full list: https://stackoverflow.com/a/5612360/11298742




- Colors  
  - DO NOT GO INTO MUCH DETAIL.
  - GREAT VIDEO (4 minutes, explains color names, hex, rgb, rgba): https://www.youtube.com/watch?v=HxztHgRN8I4

  - Some options:
    - color: red (we can not have words for every color in the world...)
    - RGB: `color: rgb(255, 0, 0);`
    - RGBA: `color: rgba(0, 255, 0, 0.5);`
    - RGB in Hexadecimal: `color: #ff0000;`




## Game: CSS dinner

CSS dinner (https://flukeout.github.io/)
- do until level 14th.


## Extra

Cascade, Specificity, Inheritance:
- https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Cascade_and_inheritance

Peter griffin:
- https://c.tenor.com/QWdPngpHxZ8AAAAd/family-guy-css.gif



