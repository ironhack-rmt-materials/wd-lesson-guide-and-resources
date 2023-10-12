
# DOM - Introduction and Selectors


<!--- 

Status: in progress



TO-DO:
- simplify: remove all concepts that are not used in the lab
- create self-guided lab/exercise ?


Note:
- link these concepts to today's lab
- Ironhack Cart Image: https://camo.githubusercontent.com/a8f2f706271dab8fc87fe27077a7fdb0561b7e2573ff684273c42a9ff34c4a2a/68747470733a2f2f692e696d6775722e636f6d2f4a38617365726d2e706e67




--->



Bad news: 
- lots of topics
Good news:
- m3: all this will be done by React
- don't need to memorize all (just be familiar)



## Cheatsheet (DOM manipulation)


DOM manipulation cheatsheet: 
https://stackblitz.com/edit/js-tdylkw?file=index.js
<!-- @todo: convert to a gist -->





## Intro

- We can see an HTML document as a hierarchy of nodes (tree): https://i.imgur.com/m08deQC.png

- Document Object Model (DOM)
  - API (Application Programming Interface) for HTML documents
    - introduce the concepts of "Interface" & "API"
  - The DOM is a fully object-oriented representation of the web page, and it can be modified from JavaScript.


- The Document object
  - Show the Document object in the dev tools:
    - Dev Tools > Console > Type 'document'
  - Documentation: https://developer.mozilla.org/en-US/docs/Web/API/Document
    - see some sample methods (eg. getElementById)


- Quick Demo:
  - go to ironhack.com + open dev tools 
  - add an id to the main title
  - in the console: `document.getElementById()` + `innerHTML`


- (optional) ask students to do the same

  1. Edit the html and add an id to any element.
    <!-- - important: in the elements panel (chrome), click out so that the changes are not lost -->
  2. Get a reference to that element
    - `document.getElementById(id)`
    - remember to store that in a variable
  3. Change the content
    - `myVariable.innerHTML = "new content"`

  Time: 5min.


- Show demo lab chronometer (show the demo & the code )
  - demo: https://sandrabosk.github.io/demo-chrono/index.html
  - index.js (with dom manipulation): https://github.com/ironhack-labs/lab-js-chronometer/blob/master/src/index.js



## Initial Setup for DOM Codealong


Initial Code: 
- https://github.com/ironhack-rmt-resources/dom-manipulation-practice
- Fork + clone + open in VS Code.
  

  <!-- 
  
  @todo: add quick exercise in the middle 
   (ex. before we see attributes)

  -->


LTs: Guided steps (with comments): 
- https://github.com/RemoteRaccoons-Ironhack-Nov-22/dom-manipulation-practice/blob/f3cea5efd73bcac65f8acde5ceb8c1d43045ddd9/js/main.js



## Search for Elements by ID: getElementById()

```js
let element = document.getElementById('some-id-goes-here');
```

Note: id must be a string



## Change the content of an element: .innerHTML property


```js
let elm = document.getElementById('string'); 
elm.innerHTML = "content";
```

- Important: it is a property (not a function)



## Search elements by Class Name: getElementsByClassName()

```js
let elements = document.getElementsByClassName(names);
```

- returns an HTMLCollection of all child elements which have all of the given class names.


- Important: returns an **HTMLCollection**
  - An HTMLCollection is an array-like object but is not an array.
  - We can not use the array methods like forEach, map, push, etc
  - But we can transform an HTMLCollection into an array. For example, with the spread operator:
      - ex.: ` const elementsArr = [...elements] `
  - An HTMLCollection in the HTML DOM is live; it is automatically updated when the document is changed.



## Search elements by Tag Name: getElementsByTagName()

```js
let elements = document.getElementsByTagName(name);
```

-  returns an HTMLCollection


##  Search one element by CSS Selector: querySelector()

- returns the first element that matches the css selector


## Search all elements by CSS Selector: querySelectorAll()

- returns a NodeList

- note: you CAN use a forEach to iterate on a NodeList
  (https://developer.mozilla.org/en-US/docs/Web/API/NodeList/forEach)




## Search on a different context


- document.method() vs elm.method()
  - explain the difference


Example:

> When called on the document object, the complete document is searched, including the root node. You may also call getElementsByClassName() on any element; it will return only elements which are descendants of the specified root element with the given class name(s).





## .innerText & .innerHTML


## Change the style: .style object

```js
elm.style.backgroundColor = 'red';
elm.style.border = '2px solid green';
```

- IMPORTANT. CSS properties composed by more than one word: camelCase

- Practice:
  - change color
  - change font-size
  - change margin




## .id property

- gets / sets 




## .className property

- gets / sets the value of the class attribute

  ```js
  element.className; // get
  element.className = "something"; // set
  ```



- EXTRA:
  - you can also read/update/toggle classes with classList
  - it is easier than interacting directly with className
    - eg. if an element has multiple classes (eg. "foo primary active") and you want to remove only one, with className you need to parse the string and split white spaces. With classList is much easier.

    ```js
    elm.classList.remove("foo");
    elm.classList.add()
    elm.classList.toggle()
    ```


