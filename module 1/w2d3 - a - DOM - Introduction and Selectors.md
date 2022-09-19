
# DOM - Introduction and Selectors






<!--- 

Status: in progress


NOTES: 

- i've changed the order of some concepts compared to students portal (first ways to select elements, then properties)

- IMPORTANT: this lesson and the next one feels a bit overwhelming for students (too many properties & methods but too little time to practice with them)

- it also took much longer than expected (it's a lot of methods) [in total, we spent 4h to see the contents, with no time left for the lab]



TO-DO:
- simplify: remove all concepts that are not used in the lab
- crate cheatsheet 
- crate self-guided lab/exercise


Suggested approach:
- intro basic concepts (getElementById(), innerHTML, style property)
- provide the students a cheatsheet or table with the main properties & methods that we see (or refer them to the students portal).
- IMPORTANT: explain the differences with HTML collection / nodelist
- pass them a challenge to solve (html doccument & some challenges to complete) [or do a codealong with those challenges]


INITIAL CODE: https://github.com/StrangerCodingThings-Ironhack-June-22/dom-manipulation-codealong/blob/main/index.html


--->





## Cheatsheet (DOM manipulation)


DOM manipulation cheatsheet: 
https://stackblitz.com/edit/js-tdylkw?file=index.js






## Intro

- We can see an HTML document as a hierarchy of nodes (tree): https://i.imgur.com/m08deQC.png

- Document Object Model (DOM)
  - API (Application Programming Interface) for HTML documents
    - introduce the concepts of "Interface" & "API"
  - provides a structured representation of the document (web page) + defines a way that the structure can be accessed from JavaScript. 
  - The DOM is a fully object-oriented representation of the web page, and it can be modified from JavaScript.


- The Document object
  - Show the Document object in the dev tools:
    - Dev Tools > Console > Type 'document'
  - Documentation: https://developer.mozilla.org/en-US/docs/Web/API/Document
    - see some sample methods (eg. getElementById)


- Quick Demo:
  - show demo on ironhack.com (note: we need to add an id manually)
    - getElementById() + innerHTML

- (optional) ask students to do the same

  1. Find an html element with an id (or edit the html)
  2. Get a reference to that element
    - `document.getElementById(id)`
  3. Change the content
    - `myVariable.innerHTML = "new content";`


- Show demo lab chronometer (show the demo & the code )
  - demo: https://sandrabosk.github.io/demo-chrono/index.html
  - index.js (with dom manipulation): https://github.com/ironhack-labs/lab-js-chronometer/blob/master/src/index.js



## Codealong

- Get boilerplate code from the students portal. Starts from this point:
    > Let’s create a folder and a couple of files to work in

- ALTERNATIVE: use this html boilerplate:
  https://github.com/StrangerCodingThings-Ironhack-June-22/dom-manipulation-codealong/blob/main/index.html

  <!--
  @Luis:
  - we usually spend a lot of time to get all working for everyone (create directories, files...)
  - instead, create a lab repo & ask students for fork + clone
  -->


## Search for Elements by ID: getElementById()

```
let element = document.getElementById('some-id-goes-here');
```

Note:
- id must be a string
- We can search on a different context (will apply to other methods we see later)
  - document.method() vs elm.method()


## Change the content of an element: .innerHTML property


```
let elm = document.getElementById('string'); 
elm.innerHTML = "content";
```

- Important: it is a property (not a function)



## Search elements by Class Name: getElementsByClassName()

```
let elements = document.getElementsByClassName(names);
```

- returns an HTMLCollection of all child elements which have all of the given class names.

- can be called on any element (not only on the document). The element on which it is called will be used as the root of the search.

- Important: returns an **HTMLCollection**
  - The HTMLCollection is an array-like object but is not an array.
    - We can not use the array methods like forEach, map, push, etc
    - We can transform it into an array. Eg., with the spread operator:
      ```
      const elementsArr = [...elements]
      ```
  - An HTMLCollection in the HTML DOM is live; it is automatically updated when the document is changed.



## Search elements by Tag Name: getElementsByTagName()

```
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







## .innerText & .innerHTML


## Change the style: .style object

```
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

```
element.className; // get
 
element.className = "something"; // set
```



- EXTRA:
  - you can also read/update/toggle classes with classList
  - it is easier than interacting directly with className
    - eg. if an element has multiple classes (eg. "foo primary active") and you want to remove only one, with className you need to parse the string and split white spaces. With classList is much easier.

    ```
    elm.classList.remove("foo");
    elm.classList.add()
    elm.classList.toggle()
    ```


