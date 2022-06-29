
# DOM - Introduction and Selectors

<!--- 

Status: in progress

Notes: 
- i've changed the order of some concepts compared to students portal (first ways to select elements, then properties)
- IMPORTANT: this lesson and the next one feels a bit overwhelming for students (too many properties & methods but too little time to practice with them)
- it also took much longer than expected (it's a lot of methods) [in total, we spent 4h to see the contents, with no time left for the lab]

To do:
- simplify: remove all concepts that are not used in the lab

Suggested approach:
- intro basic concepts (getElementById(), innerHTML, style property)
- provide the students a cheatsheet or table with the main properties & methods that we see (or refer them to the students portal).
- IMPORTANT: explain the differences with HTML collection / nodelist
- pass them a challenge to solve (html doccument & some challenges to complete) [or do a codealong with those challenges]


INITIAL CODE:
- @Luis: get initial html from here "\Ironhack\_lesson-code-samples\dom-codealong"


--->


## Warmup (refresh from previous day)

- setTimeout with timer zero (remember to fork)
  https://stackblitz.com/edit/js-kyccls?file=index.js
  - start with timer 1000ms
  - then change to 0ms

- ALTERNATIVE: ask if students have questions from chronometer lab (iteration 1)



## Intro

- We can see an HTML document as a hierarchy of nodes (tree): https://i.imgur.com/m08deQC.png

- Document Object Model (DOM)
  - API (Application Programming Interface) for HTML documents
    - introduce the concept of "Interface"
  - provides a structured representation of the document (web page) + defines a way that the structure can be accessed from JavaScript. 
  - The DOM is a fully object-oriented representation of the web page, and it can be modified from JavaScript.


- The Document object
  - Show the Document object in the dev tools:
    - Dev Tools > Console > Type 'document'
  - Documentation: https://developer.mozilla.org/en-US/docs/Web/API/Document
    - see some sample methods (eg. getElementById)


- Quick Demo:
  - getElementById() + innerHTML



## Codealong

- Get boilerplate code from the students portal. Starts from this point:
    > Let’s create a folder and a couple of files to work in

- ALTERNATIVE: use boilerplate from Manish:
  https://github.com/ManishPoduval/teaching-dom



## Search for Elements by ID: getElementById()

```
let element = document.getElementById('some-id-goes-here');
```

Note:
- id must be a string
- will return the first occurrence only



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

- returns an array of all child elements which have all of the given class names.

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


## querySelector()

- returns the first element that matches the selector


## querySelectorAll()

- returns a NodeList

- note: you CAN use a forEach to iterate on a NodeList
  (https://developer.mozilla.org/en-US/docs/Web/API/NodeList/forEach)




## Search on a different context

- document.method() vs elm.method()
  - explain the difference


## Change the style: .style object

```
elm.style.backgroundColor = 'red';
elm.style.border = '2px green solid';
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


