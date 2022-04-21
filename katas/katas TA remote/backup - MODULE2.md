# MODULE 2 KATAS

***

## WEEK 5. DAY 4.

### EASY Kata => [A Needle in the Haystack 8kyu](https://www.codewars.com/kata/56676e8fabd2d1ff3000000c/train/javascript)

```javascript
function findNeedle(haystack) {
  return "found the needle at position " + haystack.indexOf("needle")
}

// test
var haystack_1 = ['3', '123124234', undefined, 'needle', 'world', 'hay', 2, '3', true, false];
console.log( findNeedle(haystack_1) ) // 'found the needle at position 3'
```

### MID Kata => [Complementary DNA 7kyu](https://www.codewars.com/kata/complementary-dna/javascript)

```javascript
function DNAStrand(dna) {
  let newDNA = ""
  for (let i = 0; i < dna.length; i++) {
    if (dna[i] === "A") newDNA += "T"
    else if (dna[i] === "T") newDNA += "A"
    else if (dna[i] === "C") newDNA += "G"
    else if (dna[i] === "G") newDNA += "C"
  }
  return newDNA
}

// using obj & function
function DNAStrand(dna) {
  let opposites = {
    A: "T",
    T: "A",
    G: "C",
    C: "G",
  };
  function check(char) {
    return opposites[char];
  }
  return dna.split("").map(e => check(e)).join("");
}

// test
console.log(DNAStrand("ATTGC")); //"TAACG"
```

### HARD Kata => [Array Exchange 6kyu](https://www.codewars.com/kata/5353212e5ee40d4694001114/train/javascript)

```javascript
function exchangeWith(a, b) {
  let aLength = a.length;
  let bLength = b.length;

  for (let i = 0; i < aLength; i++) {
    const removedElement = a.pop();
    b.push(removedElement);
  }

  for (let i = 0; i < bLength; i++) {
    const removedElement = b.shift();
    a.unshift(removedElement);
  }
}

// shorter solution
function exchangeWith(a, b) {
  let aTemp = a.splice(0).reverse();
  let bTemp = b.splice(0).reverse();

  a.push(...bTemp);
  b.push(...aTemp);
}

// test
const myArray = ["a", "b", "c"];
const otherArray = [1, 2, 3];
exchangeWith(myArray, otherArray);
console.log(myArray); // [3, 2, 1]
console.log(otherArray); // ['c', 'b', 'a']
```

***

## WEEK 6. DAY 1.

### EASY Kata => [Get the mean of an array 8kyu](https://www.codewars.com/kata/563e320cee5dddcf77000158/train/javascript)

```javascript
function getAverage(marks){
  let sum = 0;  
  for (let i = 0; i < marks.length; i++){
    sum += marks[i]
  }
  return Math.floor(sum/marks.length)
}

function getAverage(marks){
  return Math.floor(marks.reduce((acc, e) => acc + e, 0)/marks.length)
}

console.log(getAverage([1,2,3,4,5,])) // 3
```

### MID Kata => [Flatten 7kyu](https://www.codewars.com/kata/5250a89b1625e5decd000413/train/javascript)

```javascript
// using push
var flatten = function (array) {
  let newArr = [];
  array.forEach((d1) => {
    if (typeof d1 !== "object") newArr.push(d1);
    else d1.forEach((d2) => newArr.push(d2));
  });
  return newArr;
};

// using reduce/concat
var flatten = function (array) {
  let newArr = array.reduce((acc, e) => {
    return acc.concat(e);
  }, []);
  return newArr;
};

// one liner
var flatten = function (array) {
  return array.reduce((acc, e) => acc.concat(e), []);
};

// test
console.log(
  flatten([
    [1, 2, 3],
    ["a", "b", "c"],
    [1, 2, 3],
  ])
);
// [1, 2, 3, "a", "b", "c", 1, 2, 3]
```

### HARD Kata => [Your Order, please 6kyu](https://www.codewars.com/kata/55c45be3b2079eccff00010f/train/javascript)

```javascript
function order(words) {
  let wordsArr = words.split(" ");
  let orderedArr = [];

  wordsArr.forEach((word) => {
    for (let i = 0; i < word.length; i++) {
      let character = parseInt(word[i]);
      if (!isNaN(character)) {
        orderedArr[character - 1] = word;
      }
    }
  });
  return orderedArr.join(" ");
}

// one line + regex
function order2(words) {
  return words
    .split(" ")
    .sort(
      (a, b) =>
        parseInt(a.match(/[1-9]/g).join()) - parseInt(b.match(/[1-9]/g).join())
    )
    .join(" ");
}

// test
console.log(order("is2 Thi1s T4est 3a"));
// "Thi1s is2 3a T4est"
```

***

## WEEK 6. DAY 2.

### EASY Kata => [Keep Hydrated! 8kyu](https://www.codewars.com/kata/582cb0224e56e068d800003c)

```javascript
function litres(time) {
  return Math.floor(time/2)
}

// test
console.log(litres(5.4)) // 2
```

### MID Kata => [Drone Fly-By 7kyu](https://www.codewars.com/kata/drone-fly-by/train/javascript)

```javascript
// with .replace
function flyBy(lamps, drone) {
  let lightLamps = lamps;
  for (let i = 0; i < drone.length; i++) {
    lightLamps = lightLamps.replace("x", "o");
  }
  return lightLamps;
}

// with .repeat
function flyBy(lamps, drone) {
  let lightLamps = "";
  if (drone.length > lamps.length) {
    lightLamps = "o".repeat(lamps.length);
  } else {
    lightLamps = "o".repeat(drone.length) + "x".repeat(lamps.length - drone.length);
  }
  return lightLamps;
}

// one liner
function flyBy(lamps, drone) {
  return drone.length > lamps.length
    ? "o".repeat(lamps.length)
    : "o".repeat(drone.length) + "x".repeat(lamps.length - drone.length);
}

// test
console.log(flyBy("xxxxxx", "====T")); // 'ooooox'
console.log(flyBy("x", "=T")); // 'o'
```

### HARD Kata => [Number of anagrams in an array of words 6kyu](https://www.codewars.com/kata/587e18b97a25e865530000d8)

```javascript
function anagramCounter(wordsArray) {
  let sortedArr = wordsArray.map((e) => e.split("").sort().join(""));
  // [ 'dell', 'dell', 'abc', 'abc', 'abc', 'abc' ]
  let count = 0;
  sortedArr.forEach((e, i) =>
    sortedArr.forEach((e2, i2) => {
      if (e === e2 && i !== i2) count++;
    })
  );
  return count / 2;
}

// test
let arr = ["dell", "ledl", "abc", "cba", "bca", "bac"];
console.log(anagramCounter(arr));
```

***

## WEEK 6. DAY 3.

### INTRO CSS KATA => [Battle #1. Target #1 Simply Square](https://cssbattle.dev/play/1)

```html
<div></div>
<style>
  body {
    background: #5d3a3a;
    margin: 0
  }
  div {
    width: 200px;
    height: 200px;
    background: #b5e0ba;
  }
</style>
```

### EASY CSS Kata => [Battle #1. Target #2 Carrom](https://cssbattle.dev/play/2)

```html
<div></div>
<div></div>
<div></div>
<div></div>
<style>
  body {
    margin: 0px;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    background: #62374e;
  }
  div {
    margin: 50px;
    width: 50px;
    height: 50px;
    background: #fdc57b;
  }
</style>
```

### MID CSS Kata => [Battle #6. Target #31 Equals](https://cssbattle.dev/play/31)

```html
<div class="yellow"></div>
<div class="orange"></div>
<style>
  body {
    margin: 50px;
    display: flex;
    justify-content: space-around;
    background: #AA445F
  }
  div {
    width: 100px;
    height: 200px;
    background: #dd6b4d;
  }
  .yellow {
    background: #F7EC7D;
    border-top-left-radius: 200px;
    border-bottom-left-radius: 200px
  }
  .orange {
    background: #E38F66;
    border-top-right-radius: 200px;
    border-bottom-right-radius: 200px
  }
</style>
```

### HARD CSS Kata => [Battle #1. Target #4 Ups n Downs](https://cssbattle.dev/play/4)

```html
<div class="container top">
  <div class="inner top-round"></div>
  </div>
<div class="container bottom">
  <div class="inner bottom-round"></div>
  <div class="inner bottom-round"></div>
</div>
<style>
  body {    
    margin: 0;
    background: #62306D
  }
  .container {
    display: flex;
    height: 50%;
  }
  .top {
    align-items: flex-end;
    justify-content: center;
  }
  .bottom {
    align-items: flex-start;
    justify-content: space-around;
  }
  .inner {
    width: 100px;
    height: 100px;
    background: #F7EC7D;
  }
  .top-round {
    border-top-left-radius: 200px;
    border-top-right-radius: 200px
  }
  .bottom-round {
    border-bottom-right-radius: 200px;
    border-bottom-left-radius: 200px
  }
 </style>
```

***

## WEEK 6. DAY 4.

### EASY Kata => [Remove the time 8kyu](https://www.codewars.com/kata/56b0ff16d4aa33e5bb00008e)

```javascript
function shortenToDate(longDate) {
  let shortDate = ""
  for (let i = 0; i < longDate.length; i++) {
    if (longDate[i] === ",") break;
    shortDate += longDate[i]
  }
  return shortDate
}

// with slice & indexOf
function shortenToDate(longDate) {
  return longDate.slice(0, longDate.indexOf(","))
}

// test
let date = "Tuesday January 29, 10pm"
console.log( shortenToDate(date) ) // "Tuesday January 29"
```

### MID Kata => [Disemvowel Trolls 7kyu](https://www.codewars.com/kata/52fba66badcd10859f00097e)

```javascript
function disemvowel(str) {
  let newStr = "";
  for (let i = 0; i < str.length; i++) {
    switch(str[i].toLowerCase()) {
      case "a":
      case "e":
      case "i":
      case "o":
      case "u":
        break;
      default:
        newStr += str[i];
    }
  }
  return newStr;
}

// with regex
function disemvowel(str) {
  let newStr = "";
  for (let i = 0; i < str.length; i++) {
    if (!str[i].match(/[aeiouAEIOU]/gi)) {
      newStr += str[i];
    }
  }
  return newStr;
}

// one liner with .replace and regex
function disemvowel(str) {
  return str.replace(/[aeiouAEIOU]/gi, "")
}

// test
console.log( disemvowel("This website is for losers LOL!") ) 
// "Ths wbst s fr lsrs LL!"
```


### HARD Kata => [Find the odd int 6kyu](https://www.codewars.com/kata/find-the-odd-int/train/javascript)

```javascript
function findOdd(A) {
  let oddNumber = 0;

  for (let i = 0; i < A.length; i++) {
    let count = 0;
    A.forEach((e) => {
      if (A[i] === e) count++;
    });
    if (count % 2 === 1) {
      oddNumber = A[i];
      break; // for loop and break for better performance
    }
  }

  return oddNumber;
}

// one liner
function findOdd2(A) {
  return A.find((e) => A.filter((e2) => e === e2).length % 2 === 1);
}

// test
console.log(findOdd([20, 1, -1, 2, 5, -2, 3, 3, 5, 5, 1, 2, 4, 20, 4, -1, -2])); // 5
```

***

## EXTRA KATAS

### HARD KATA => [Find the missing letter 6kyu](https://www.codewars.com/kata/find-the-missing-letter/javascript)

```javascript
function findMissingLetter(array) {
  for (let i = 0; i < array.length - 1; i++) {
    if (array[i + 1].charCodeAt() - array[i].charCodeAt() === 2) {
      return String.fromCharCode(array[i].charCodeAt() + 1);
    }
  }
}

// one liner with filter
function findMissingLetter(array) {
  return String.fromCharCode(
    array
      .filter((e, i) =>
        array[i + 1] ? array[i + 1].charCodeAt() - e.charCodeAt() === 2 : false
      )
      .join()
      .charCodeAt() + 1
  );
}

// test
console.log(findMissingLetter(["a", "b", "c", "d", "f"])); // 'e'
```

### HARD Kata => [Clocky Mc Clock-Face 6kyu](https://www.codewars.com/kata/clocky-mc-clock-face/javascript)

```javascript
var whatTimeIsIt = function (angle) {
  // 360 degrees in a circle. 720 minutes in 12 hour.
  let totalMinutes = angle * 2;

  let hours = Math.floor(totalMinutes / 60);
  let minutes = Math.floor(totalMinutes % 60);

  let hoursFixed = ("0" + hours).slice(-2);
  let minutesFixed = ("0" + minutes).slice(-2);

  if (hours === 0) hoursFixed = "12";

  return `${hoursFixed}:${minutesFixed}`;
};

// test
console.log(whatTimeIsIt(0)); //  "12:00"
console.log(whatTimeIsIt(360)); //  "12:00"
console.log(whatTimeIsIt(90)); //  "03:00"
```

### HARD Kata => [Street Fighter 2 - Character Selection 6kyu](https://www.codewars.com/kata/street-fighter-2-character-selection/train/javascript)

```javascript
function streetFighterSelection(fighters, position, moves) {
  let charMove = [];

  // position[0] = y axis position
  // position[1] = x axis position

  moves.forEach((e) => {
    switch (e) {
      case "up":
        position[0] = 0;
        break;
      case "down":
        position[0] = 1;
        break;
      case "right":
        position[1] === 5 ? position[1] = 0 : position[1] += 1;
        break;
      case "left":
        position[1] === 0 ? position[1] = 5 : position[1] -= 1;
        break;
    }
    charMove.push(fighters[position[0]][position[1]]);
  });
  return charMove;
}

// test
let fighters = [
  ["Ryu", "E.Honda", "Blanka", "Guile", "Balrog", "Vega"],
  ["Ken", "Chun Li", "Zangief", "Dhalsim", "Sagat", "M.Bison"],
];
let moves = ["up", "left", "right", "left", "left"];

console.log(streetFighterSelection(fighters, [0, 0], moves));
// ['Ryu', 'Vega', 'Ryu', 'Vega', 'Balrog']);
```