
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
  ```
  const myNewImg = document.createElement('img');
  ```

- step2: add content or modify (ex. innerHTML...)
  ```
  myNewImg.setAttribute("src", "./images/something.jpg")
  ```

- step3: append to the dom: `parentElm.appendChild()`
  ```
  parentElm.appendChild(myNewImg)
  ```


## Remove an element from the DOM
- `parent.removeChild(myElm);`


## Clear html
- Clear an existing element: `element.innerHTML = ''`


## Evemts 

Explain:
- what are events
  > "Events are actions that happen in the system you are programming. The system tells you about so your code can react to them".
- examples of events
  - Document (DOMContentLoaded, ...)
  - mouse events (ex. click, mouseover...)
  - keyboard events (ex. keydown, keypress, keyup)
- events can be attached to an html element (or multiple)

- 3 ways to attach events to a dom element:
  - Inline event handlers (don't use)
    - Problem: html+js
    - Also, some systems disallow inline JS for security reasons.
    - `<button onclick="bgChange()">Press me</button>`
  - Event handler properties
    - limitation: you can't add more than one handler for a single event.
    - `btn.onclick = () => {}`
  -  Using addEventListener (recommended)
    - Allows attaching multiple event handlers
    -  `btn.addEventListener('click', () => {})`


- JS Events cheatsheet:  
  - https://stackblitz.com/edit/js-a5gh8b?file=index.js




## Inputs


- Inputs manipulation (need it for `LAB | DOM Ironhack Cart`)
  - Getting a current value from the input field
    - `priceElm.value`
  - Know on which DOM element the event was fired
    - `onclick = function(event) {}`
      - Event interface ("represents an event which takes place in the DOM")
    - `event.target`



## (extra) event bubbling
- Today's lab (bonus iteration): they will need to add events to elements created dynamically
- Explain what is event bubbling (briefly)
- Alternative: tell students to do some research (ex. how to add a click event to a button dynamically created)
  - example: https://stackoverflow.com/a/34896325/11298742




## Scraping a Website (skip)
