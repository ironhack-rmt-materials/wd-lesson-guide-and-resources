
# DOM - Manipulation

<!--- 

Status: 
- summary ready
- section "events" quite comprehensive

--->


## Attributes
- get: element.getAttribute(attributeName);
- modify and create: element.setAttribute(name, value);
- remove: element.removeAttribute(attrName);



## Adding elements to the DOM

- step1: create the element:
  ```js
  const myNewImg = document.createElement('img');
  ```

- step2: add content or modify (ex. innerHTML...)
  ```js
  myNewImg.setAttribute("src", "./images/something.jpg")
  ```

- step3: append to the dom: `parentElm.appendChild()`
  ```js
  parentElm.appendChild(myNewImg)
  ```


## (skip) Remove an element from the DOM
- `parent.removeChild(myElm);`
- note: parentContainer needs to be the direct parent.


## (skip) Clear html
- Clear an existing element: `element.innerHTML = ''`



## Evemts 

Explain:
- what are events
  > "Events are actions that happen in the system you are programming. The system tells you about so your code can react to them".

- examples of events
  - mouse events (ex. click, mouseover...)
  - keyboard events (ex. keydown, keypress, keyup)
  - Document (DOMContentLoaded, ...)
- events can be attached to an html element (or multiple)

- (brief) 3 ways to attach events to a dom element:
  - Inline event handlers (don't use)
    - Problem: html+js
    - Also, some systems disallow inline JS for security reasons.
    - `<button onclick="bgChange()">Press me</button>`
    - IIFE: `<button onclick="(function(){ console.log('user clicked!!')})()">Press me</button>`
  - Event handler properties
    - limitation: you can't add more than one handler for a single event.
    - `btn.onclick = () => {}`
  -  Using addEventListener (recommended)
    - Allows attaching multiple event handlers
    -  `btn.addEventListener('click', () => {})`



Demo: append a paragraph everytime the user clicks on a button

  1. Detect click event:

    ```js
    const btn = document.getElementById("button-1");

    btn.addEventListener("click", () => {
        console.log("user has clicked on a button");
    })
    ```

  2. Append paragraph

    ```js
    //append paragraph
    const newP =  document.createElement("p");
    newP.innerText = "this p has been created dynamically";
    parentElm.appendChild(newP);

    ```


List of possible events:
- https://www.w3schools.com/jsref/dom_obj_event.asp



Practice & Research: detect keyboard events
- Goal: 
  - Add functionality to detect if the user presses "spacebar"
  - Ex. if user presses spacebar, `console.log("you've pressed the spacebar")`
- (bonus 1): detect also arrow keys (down, up, left, right)
- (bonus 2): if user presses spacebar, add a div to the dom.
- (bonus 3): if user presses arrow up, move that div (hint: `position: relative`)
Time: 15min.

<!-- note: students will need to use the event object (which is what we'll explain next) -->



Event object:
  - Event object: automatically passed to event handlers to provide extra features and information.
  - MDN: https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events#event_objects

  ```js
  btn.addEventListener('click', (e) => {
    console.log(e);
  });
  ```


Detect spacebar:

  ```js
  document.addEventListener('keydown', (e) => {
      if (e.code === "Space") {
          console.log("user pressed spacebar")
      } else {
          console.log("user pressed other key....")
      }
  });
  ```



## Attach an event listener to multiple elements


Practice: attach an event listener to multiple elements

- Iteration 1: add an event listener to detect if the user clicks on any title.

- Bonus: when the user clicks, modify the css of that title.


Example:

  ```js
  const titles = document.querySelectorAll(".interactive-title");

  titles.forEach( (elm) => {
      elm.addEventListener("click", () => {
          elm.classList.toggle("active");
      })
  });
  ```





## Cheatsheet


JS Events cheatsheet:  
  - https://stackblitz.com/edit/js-a5gh8b?file=index.js





## (skip) Inputs


- Inputs manipulation (need it for `LAB | DOM Ironhack Cart`)
  - Getting a current value from the input field
    - `priceElm.value`
    - `typeof priceElm.value` -- STRING

  - Know on which DOM element the event was fired
    - `onclick = function(event) {}`
      - Event interface ("represents an event which takes place in the DOM")
    - `event.target`



## (skip) Event bubbling


- Explain what is event bubbling (briefly)

- Diagram: https://miro.medium.com/v2/resize:fit:640/format:webp/1*03qD5hLMr4DkyCrCohsrqw.png



## (skip) Detect Events on elements created dynamically

- Today's lab (bonus iteration): they will need to add events to elements created dynamically


- Tell students to do some research (ex. js how to add a click event to a button dynamically created)
  - example: https://stackoverflow.com/a/34896325/11298742


- ALTERNATIVE: they can also add the event listener when a new product is created. For example:

  ```js
  const removeBtn = newProduct.querySelector(".btn-remove")
  removeBtn.addEventListener();
  ```



<!--
@Luis: 

event bubbling + "Detect Events on elements created dynamically":
- take a bit of time & students find it confussing
- keep it brief & generic
- give some hints so that they do research

TO-Do:
- create a quick code example with "Detect Events on elements created dynamically"

-->



## (skip) Scraping a Website


## Extra resources

Video: Javascript Dom Manipulation | Javascript Tutorial For Beginners
(developedbyed, 17min.)
https://www.youtube.com/watch?v=wiozYyXQEVk

<!-- @Luis: includes some interesting examples that we can use in demo -->





