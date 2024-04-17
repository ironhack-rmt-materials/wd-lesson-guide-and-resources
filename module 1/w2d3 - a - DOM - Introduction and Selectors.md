
# DOM - Introduction and Selectors


<!---

Status: ready


TO-DO:
- simplify: remove all concepts that are not used in the lab


--->





## Cheatsheet (DOM manipulation)


DOM manipulation cheatsheet:
https://stackblitz.com/edit/js-tdylkw?file=index.js
<!-- @todo: convert to a gist -->





## Intro

- We can see an HTML document as a hierarchy of nodes (tree): https://i.imgur.com/m08deQC.png


- Document Object Model (DOM)
  - The DOM is a fully object-oriented representation of the web page, and it can be modified from JavaScript.


- Example: today's lab (IronContacts): 
  - https://camo.githubusercontent.com/2c705dace5f645575f909f42fcf8adb3b3c02933526fda6a3574450825855373/68747470733a2f2f656475636174696f6e2d7465616d2d323032302e73332e65752d776573742d312e616d617a6f6e6177732e636f6d2f7765622d6465762f6c6162732f6c61622d646f6d2d69726f6e636f6e74616374732f30302d6c61622d646f6d2d69726f6e636f6e74616374732d696e74726f2e676966



- The Document object
  - Show the Document object in the dev tools:
    - Dev Tools > Console > Type 'document'
  - Documentation: https://developer.mozilla.org/en-US/docs/Web/API/Document
    - see some sample methods (eg. getElementById)


- Quick Demo:
  - go to ironhack.com + open dev tools
  - add an id to the main title
  - in the console: `document.getElementById()` + `innerText`


- Good & Bad news:
  - Bad news: lots of topics
  - Good news:
    - don't need to memorize all (just be familiar)
    - m2: all this will be done by React




## Initial Setup for DOM Codealong


Initial Code:
- https://github.com/ironhack-rmt-resources/dom-manipulation-practice
- Fork + clone + open in VS Code.



LTs: Guided steps (with comments):
  <!-- @LT: follow this steps -->
- https://github.com/RemoteRaccoons-Ironhack-Nov-22/dom-manipulation-practice/blob/f3cea5efd73bcac65f8acde5ceb8c1d43045ddd9/js/main.js




## Search for Elements by ID: `getElementById()`

```js
let element = document.getElementById('some-id-goes-here');
```

Note: id must be a string




## Change the content of an element: `.innerText` property


```js
let elm = document.getElementById('string');
elm.innerText = "content";
```

- Important: it is a property (not a function)




## Search elements by Class Name: `getElementsByClassName()`

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




## Search elements by Tag Name: `getElementsByTagName()`

```js
let elements = document.getElementsByTagName(name);
```

- returns an HTMLCollection



##  Search one element by CSS Selector: `querySelector()`

- returns the first element that matches the css selector



## Search all elements by CSS Selector: `querySelectorAll()`

- returns a NodeList

- note: you CAN use a forEach to iterate on a NodeList
  (https://developer.mozilla.org/en-US/docs/Web/API/NodeList/forEach)




## Practice: selecting elements from the DOM

<!--
@LT:
- before doing the exercise, make a quick demo on how to change the style
- ex. elm.style.background = "orange"
-->

Instructions: https://stackblitz.com/edit/web-platform-ydtmzw?file=script.js

Time: 10-15min.

Solution: https://stackblitz.com/edit/web-platform-doucbe?file=script.js




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


