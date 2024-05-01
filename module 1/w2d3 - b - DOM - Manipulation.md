
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



## JS Evemts 

Explain:
- what are events
  > "Events are actions that happen in the system you are programming. The system tells you about so your code can react to them".

- examples of events
  - mouse events (ex. click, mouseover...)
  - keyboard events (ex. keydown, keypress, keyup)
  - Document (DOMContentLoaded, ...)
  - Full list: https://www.w3schools.com/jsref/dom_obj_event.asp

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



## Demo: append a paragraph everytime the user clicks on a button

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




## Practice & Research: detect keyboard events
- Initial Code: https://stackblitz.com/edit/web-platform-oz1yyy?file=script.js
- Goal: 
  - Add functionality to detect if the user presses "spacebar"
  - Ex. if user presses spacebar, `console.log("you've pressed the spacebar")`
  <!-- Note: to test your code, make sure you click on the html document before you press space  -->
- (bonus 1): detect also arrow keys (down, up, left, right)
- (bonus 2): if user presses spacebar, add a div to the dom.
- (bonus 3): if user presses arrow up, move that all the divs (hint: `position: relative`)
Time: 15min.

Solution: https://stackblitz.com/edit/web-platform-6bfg8u?file=script.js
Solution bonus 1: https://stackblitz.com/edit/web-platform-jbaohu?file=script.js
Solution bonus 2: https://stackblitz.com/edit/web-platform-w2w9r7?file=script.js
Solution bonus 3: https://stackblitz.com/edit/web-platform-mxx7fn?file=script.js

<!-- note: students will need to use the event object (which is what we'll explain next) -->




## Event object

- Event object: automatically passed to event handlers to provide extra features and information.

- MDN: https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events#event_objects

  ```js
  btn.addEventListener('click', (e) => {
    console.log(e);
  });
  ```


## Example: detect spacebar

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


Example: 

```js
  const allBtn = document.querySelectorAll(".btn");

  allBtn.forEach( (elm) => {
      elm.addEventListener("click", () => {
          console.log("click on a generic button...")
      });
  });
```



## (extra) Practice: attach an event listener to multiple elements

Instructions: https://stackblitz.com/edit/web-platform-fppahh?file=script.js

Time: 15min.

Solution: https://stackblitz.com/edit/web-platform-wc6dzu?file=script.js





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

<!-- not needed for today's lab -->

- Explain what is event bubbling (briefly)

- Diagram: https://miro.medium.com/v2/resize:fit:640/format:webp/1*03qD5hLMr4DkyCrCohsrqw.png



## (skip) Detect Events on elements created dynamically

<!-- not needed for today's lab -->

- Today's lab (bonus iteration): they will need to add events to elements created dynamically


- Tell students to do some research (ex. js how to add a click event to a button dynamically created)
  - example: https://stackoverflow.com/a/34896325/11298742


- ALTERNATIVE: they can also add the event listener when a new product is created. For example:

  ```js
  const removeBtn = newProduct.querySelector(".btn-remove")
  removeBtn.addEventListener();
  ```



<!--

event bubbling + "Detect Events on elements created dynamically":
- take a bit of time & students find it confussing
- keep it brief & generic
- give some hints so that they do research

TO-Do:
- create a quick code example with "Detect Events on elements created dynamically"

-->




## Extra resources

Video: Javascript Dom Manipulation | Javascript Tutorial For Beginners
(developedbyed, 17min.)
https://www.youtube.com/watch?v=wiozYyXQEVk

<!-- includes some interesting examples that we can use in demo -->



