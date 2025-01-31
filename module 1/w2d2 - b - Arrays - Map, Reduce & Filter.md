# Arrays - Map, Reduce & Filter


<!-- 

Status: ready

@todo:
- create cheatsheet +++
- some of the activities in pairs ?

-->



## Intro exercise (before explaining map): 

- Intro: Any basket fan? Michael Jordan last shot with the Bulls: 
  - https://pbs.twimg.com/media/EYWEL13XkAcHnxm?format=jpg&name=4096x4096


- Practice: forEach

  Instructions: https://stackblitz.com/edit/js-nmrwqu?file=index.js

  Time: 10min.


  <!-- 
  
  @LT: 
  
  - give some HINTS before we start 
  - declare an empty array + keep adding elements to that array
  
  -->

  Solution: https://stackblitz.com/edit/js-k66y7n?file=index.js

  
- Solve together [5min.]






## map()


- Explain map() method.
  
  - .map() is useful whenever we need to apply a transformation to all elements in an array.
  
  - diagram: https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_c465728a5460c8d562936d4f1b5d18cc.png 

  - notice: the number of elements in the new array is the same.

  - see documentation (MDN)
    - very similar to .forEach()



- Example: map() with an array of numbers
  - Solve the intro exercise using .map().

  ```js
    const baskets = [11, 14, 7, 12, 9, 12]; // regular (2 point) baskets in his last games with the bulls

    const newArray = baskets.map(function (amount) {
      return amount * 2;
    });

    console.log(newArray);
  ```

  - NOTE: .map() returns a new array but DOES NOT modify the original 



### Practice: map with an array of strings (transform names to uppercase)

- Instructions: https://stackblitz.com/edit/js-dm5iu3?file=index.js

- Time: 10min. + solve together.

- Solutions:
  - with map: https://stackblitz.com/edit/js-i296ku?file=index.js
  - with for loop: https://stackblitz.com/edit/js-reuufm?file=index.js
  - with forEach: https://stackblitz.com/edit/js-ypkht5?file=index.js



### Practice: map() with an array of objects (create an array with the names of all students).


- Instructions: https://stackblitz.com/edit/js-ylftrs?file=index.js

- Time: 10min. + solve together.

- Solution: https://stackblitz.com/edit/js-9urdsg?file=index.js




### Bonus: map() with an array of objects (create an array with the points scored in each game).

- Instructions: https://stackblitz.com/edit/js-p3k5so?file=index.js

- Time: 10min.

- Solution: https://stackblitz.com/edit/js-ejcare?file=index.js







## reduce()


<!--
- DEMO EXPLANATION .reduce() with numbers:

// const baskets = [4, 6, 7, 0, 10];

https://stackblitz.com/edit/ih-reduce-method-explained?file=index.js


-->


- Intro (helps understand reduce better):


```js
  const baskets = [4, 6, 7, 0, 10];

  // Task:
  // Calculate the total amount of baskets
  //
  // Expected result: 27
  //


  // Option 1: with a forEach()
  let total = 0;
  baskets.forEach((element) => {
    // total = total + element;
    total += element;
  });

```


- Signature:

  ```js
    reduce(function(accumulator, currentValue) { /* ... */ }, initialValue)
  ```



- Example: 

  ```js
  array.reduce(function (accumulator, currentValue) {
      return accumulator + currentValue;
  });
  ```

  <!--
  Steps to follow:
  - signature + add initial value 0
  - console.log(currentValue)
  - console.log(accumulator)
  -->

  - accumulator is an accumulated value of each call
    - (IMPORTANT) In the first round, it's assumed it’s the first value from the array unless we state differently (which we will see how).

  - currentValue is the current element in each iteration that will be added to the accumulator.



- Setting an initial value:

  ```js
      arr.reduce( function(acc, curr){ ... }, initialValue)
  ```




### Demo: reduce() with an array of strings

  <!-- optional / quick extra example -->

  ```js
  const words = ["the", "quick", "brown", "fox"];


  const sentence = words.reduce(function(acc, currentValue){
    return acc + " " + currentValue;
  }, "")

  console.log(sentence);
  ```



### Practice: reduce() with an array objects

  - Instructions: https://stackblitz.com/edit/js-aervwj?file=index.js
    - IMPORTANT: in this case we need to set an initial value.
  - Time: 15min.

  - Solution: https://stackblitz.com/edit/js-xufcpn?file=index.js
  - Solution with bonus: https://stackblitz.com/edit/js-zb2mxv?file=index.js


  <!--

  Greatest Movies Lab: 
  
  They'll need to pass extra tests:
  - ex. what happens if a recipe does not have the property `calories`
  - ex. returning the average in a specific format (rounded to 2 decimals)
  
  -->


### Bonus: reduce() with an array of objects

  - Instructions: https://stackblitz.com/edit/js-gcvjvufp?file=index.js

  - Time: 15min.

  - Possible solution: https://stackblitz.com/edit/js-vgpkmd?file=index.js





## filter()

-  iterates through an array and creates a new array with all elements that pass the condition we set


- Example 1:

  ```js
  const cities = [
    'miami',
    'barcelona',
    'madrid',
    'amsterdam',
    'berlin',
    'sao paulo',
    'lisbon',
    'mexico city',
    'paris'
  ];
  ```

  TASK:
  - get only the cities with 6 letters
  - (bonus) get only the cities that contain letter 's'




- Example 2: with an array of objects


  ```js

    const people = [
      { name: 'alice', age: 30 },
      { name: 'bob', age: 18 },
      { name: 'charlie', age: 49 },
      { name: 'david', age: 21 },
      { name: 'emma', age: 17 }
    ];

  ```

  TASK: 
  - get an array with all people above 20.

  Solution: https://stackblitz.com/edit/js-bdtvhz?file=index.js





## Identify & chaining:

  - Identifying which method we can use can be tricky. 
    - Solution: practice.

  - Visual cheatsheet with some array methods:
    - https://res.cloudinary.com/practicaldev/image/fetch/s--sYEjzdnw--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/sr8koff729gxcvpnoty6.jpeg

  - We can also chain array methods. 
    - Ex: `.filter().reduce()`
    - Ex: `.filter().map()`



## Mutating vs. non-mutating methods


- `.map()`, `.filter()` and `.reduce()`  don't modify the original 

- (they don't mutate the original array but rather create a new array)





## Extra:

- Cheatsheet
  - just google images "js array methods"

  - Cheatsheet Meme (map vs filter vs reduce): 
    https://res.cloudinary.com/practicaldev/image/fetch/s--fR01rwJz--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/3158n4nhe7gt24wvl2u4.png

- Mutating vs. non-mutating methods:
  https://miro.medium.com/max/1400/1*hav8uvwoznX0JITWDOCvFw.png


- Cheatsheet (gist) with array methods (includes sort):
  - https://gist.github.com/TA-Remote/505bb6969851737d76603143a6b45c55


- LinkedIn article - Javascript​: Array methods cheatsheet
  - https://www.linkedin.com/pulse/javascript-array-methods-cheatsheet-igor-gonchar/?trk=read_related_article-card_title
  - https://media.licdn.com/dms/image/C5612AQE90tEudo8eUg/article-inline_image-shrink_1500_2232/0/1623137760585?e=1689206400&v=beta&t=UW_whrS3qHniCQtY8lXQhXOAnctNXd32IvXrDgB2m9c


- Map, Filter and Reduce - JavaScript Tutorial (Lydia Hallie, 10min.)
  - https://www.youtube.com/watch?v=UXiYii0Y7Nw


- Slides (in progress):
  - https://docs.google.com/presentation/d/1fwO9zcU-xCZoS4EYz4GSMc-na5Ugy2ETTZ-rwQI7n1k/edit?usp=sharing



