
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


## Remove an element from the DOM
- `parent.removeChild(myElm);`
- note: parentContainer needs to be the direct parent.


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



Example: append a paragraph everytime the user clicks on a button

  ```js
  const btn = document.getElementById("button-1");

  btn.addEventListener("click", () => {
      console.log("user has clicked on a button");

      //append paragraph
      const newP =  document.createElement("p");
      newP.innerText = "this p has been created dynamically";
      parentElm.appendChild(newP);

  })
  ```

Event object:
  - Event object: automatically passed to event handlers to provide extra features and information.
  - MDN: https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events#event_objects

  ```js
  btn.addEventListener('click', (e) => {
    console.log(e);
  });
  ```



JS Events cheatsheet:  
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

<!--
@Luis: 

event bubbling + "Detect Events on elements created dynamically":
- take a bit of time & students find it confussing
- keep it brief & generic
- give some hints so that they do research

TO-Do:
- create a quick code example with "Detect Events on elements created dynamically"
  (they will need it for last bonus iteration)


-->




## Scraping a Website (skip)
