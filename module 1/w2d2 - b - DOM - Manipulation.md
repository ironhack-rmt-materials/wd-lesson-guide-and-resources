
# DOM - Manipulation

<!--- 

Status: 
- summary ready
- section "events" quite comprehensive

--->


SUMARY:
- Operating with attributes
  - get: element.getAttribute(attributeName);
  - modify and create: element.setAttribute(name, value);
  - remove: element.removeAttribute(attrName);

- Create a DOM object
  - step1: create the element --> createElement('h2');
  - step2: add content --> ex. innerHTML
  - step3: append to the dom --> appendChild()
- remove element from the DOM
- Clear an existing element (`element.innerHTML = ''`)
- Events (see notes below)
- Inputs manipulation (need it for `LAB | DOM Ironhack Cart`)
  - Getting a current value from the input field
  - Know on which DOM element the event was fired
    - `onclick = function(event) {}`
      - Event interface ("represents an event which takes place in the DOM")
    - `event.target`
- (extra exercise) Scraping a Website



## Events in JavaScript

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

- (extra) event bubbling

