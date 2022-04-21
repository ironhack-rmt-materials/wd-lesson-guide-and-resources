# MODULE 3 KATAS

***

## WEEK 8. DAY 3

### EASY Kata => [Beginner - Lost Without a Map 8kyu](https://www.codewars.com/kata/57f781872e3d8ca2a000007e/train/javascript)

```javascript
function maps(x){
  return x.map(e => e * 2)
}

// test
console.log( maps([1, 2, 3]) ) // [2, 4, 6]
```

### MID Kata => [Sum without highest and lowest number 8kyu](https://www.codewars.com/kata/576b93db1129fcf2200001e6/train/javascript)

```javascript
function sumArray(array) {
  if (!array) return 0
  let sum = 0;
  array.sort((a,b) => a - b)
  for (let i = 1; i < array.length-1; i++) {
    sum += array[i]
  }
  return sum
}

function sumArray(array) {
  if (!array || array.length < 3) return 0
  return array.reduce((a,b) => a + b, 0) - Math.min(...array) - Math.max(...array)
}


// test
console.log( sumArray([ 6, 2, 1, 8, 10 ]) ) // 16
```

### HARD Kata => [Bit Counting 6kyu](https://www.codewars.com/kata/526571aae218b8ee490006f4)

```javascript
var countBits = function (n) {
  let bin = n.toString(2);
  let sum = 0;
  for (let i = 0; i < bin.length; i++) {
    sum += parseInt(bin[i]);
  }
  return sum;
};

// one liner with reduce
var countBits = function(n) {
  return n.toString(2).split("").reduce((a,b) => (+a) + (+b), 0)
};

//Another solution without toString(2)
var countBits = function(number) {
  if (number === 0) {
    return 0
  }
  let bit = '';
  // basically what happens here is that you take your number and first check if it's greater than 0
  while (number > 0) {
  // If it is greater do a modulo and put what's left in the variable bit (either 0 or 1)
    let newBit = number % 2
    bit = newBit + bit;
    // then you divide your number by 2 and the condition will check again if the number is greater than 0 or not.
    number = Math.floor(number/2)
  }
  // Once the number is no longer greater than 0 the while stops and you are left with a variable bit that would look something like
  // '0001' (depending on the original number). You then check the number of 1 in this variable and return the length.
  return   bit.match(/1/g).length
};

// test
console.log( countBits(7) ) // 3
```

***

## WEEK 8. DAY 4

### EASY Kata => [Abbreviate a Two Word Name 8kyu](https://www.codewars.com/kata/57eadb7ecd143f4c9c0000a3)

```javascript
function abbrevName(name){
  const arr = name.split(" ")
  return `${arr[0][0].toUpperCase()}.${arr[1][0].toUpperCase()}`
}

// test
console.log( abbrevName("harry potter") ) // H.P
```

### MID Kata => [Jaden Casing Strings 5kyu](https://www.codewars.com/kata/jaden-casing-strings/train/javascript)

```javascript
String.prototype.toJadenCase = function () {
  let strToArr = this.split(" ");
  let jadenArr = strToArr.map((word) => word[0].toUpperCase() + word.slice(1));
  let arrToStr = jadenArr.join(" ");
  return arrToStr;
};

// one line
String.prototype.toJadenCase = function () {
  return this.split(" ").map((e) => e[0].toUpperCase() + e.slice(1)).join(" ");
};

// test
let str = "How can mirrors be real if our eyes aren't real";
console.log( str.toJadenCase() );
// "How Can Mirrors Be Real If Our Eyes Aren't Real"
```

### HARD Kata => [Pete, the baker 5kyu](https://www.codewars.com/kata/525c65e51bf619685c000059)

```javascript
function cakes(recipe, available) {
  const ings = Object.keys(recipe);
  const availablePerIng = ings.map(eachIng => {
    return available[eachIng] ? available[eachIng] / recipe[eachIng] : 0;
  });
  return Math.floor(Math.min(...availablePerIng));
}

//test
let recipe = { flour: 500, sugar: 200, eggs: 1 };
let available = { flour: 1200, sugar: 1200, eggs: 5, milk: 200 };
console.log(cakes(recipe, available)); // 2

```

***

## WEEK 9. DAY 1

### EASY Kata => [Fake Binary 8kyu](https://www.codewars.com/kata/57eae65a4321032ce000002d)

```javascript
function fakeBin(x){
  let bin = ""
  for (let i = 0; i < x.length; i++) {
    x[i] < 5 ? bin += "0" : bin += "1"
  }
  return bin
}

function fakeBin2(x){
  return x.split("").map(e => e < 5 ? "0" : "1").join("")
}

// test
console.log( fakeBin('45385593107843568') ) // '01011110001100111'
```

### MID Kata => [Exes and Ohs 7kyu](https://www.codewars.com/kata/55908aad6620c066bc00002a)

```javascript
function XO(str) {
  let counterO = 0, counterX = 0;
  for (let i = 0; i < str.length; i++) {
    str[i].toLowerCase() === "o" ? counterO++ : null;
    str[i].toLowerCase() === "x" ? counterX++ : null;
  }
  return counterO === counterX;
}

// test
console.log( XO("xxOo") ) // true
console.log( XO("xxxm") ) // false
```

### HARD Kata => [Valid Parentheses 5kyu](https://www.codewars.com/kata/52774a314c2333f0a7000688)

```javascript
// with recursive function
function validParentheses(parens) {
  function check() {
    for (let i = 0; i < parens.length - 1; i++) {
      if (parens[i] === "(" && parens[i + 1] === ")") {
        parens = parens.slice(0, i) + parens.slice(i + 2);
        check();
      }
    }
  }
  check();
  return parens.length === 0;
}

function validParentheses(parens) {
  for(let i = 0; i < parens.length - 1; i++){
    if(parens[i] === "(" && parens[i + 1] === ")"){
      parens = parens.slice(0, i) + parens.slice(i + 2);
      i = -1
    }
  }
  return parens.length === 0
}

//test
console.log( validParentheses( "())" ) ) //  false
console.log( validParentheses( "(())(())()" ) ) //  true

```

***

## WEEK 9. DAY 2

### CSS KATA => [Battle #5. Target #30. Horizon](https://cssbattle.dev/play/30)

```html
<div class="line-one yellow"></div>
<div class="line-one orange"></div>
<div class="line-two red"></div>
<div class="line-two purple"></div>

<style>
  
  body {
    margin: 0
  }
  .line-one {
    height: 50px;
  }
  .line-two {
    height: 100px;
  }
  .yellow {
    background-color: #F7EC7D
  }
  .orange {
    background-color: #E38F66
  }
  .red {
    background-color: #AA445F
  }
  .purple {
    background-color: #62306D
  }
  
</style>
```

### CSS KATA => [Battle #2. Target 13. Totally Triangle](https://cssbattle.dev/play/13)

```html
<div></div>
<style>
  
  body {
    margin:0;
    background-color: #0B2429
  }
  
  div {
    width: 0px;
    height: 0px;
    background-color: #F3AC3C;
    border-style: solid;
  	border-width: 140 140 0 0;
  	border-color: transparent #0B2429;
  }
  
</style>
```

### CSS KATA => [Battle #2. Target #18. Matrix](https://cssbattle.dev/play/18)

```html
<div class="orange"></div>
<div class="cream"></div>
<div class="orange"></div>
<div class="cream"></div>
<div class="cream"></div>
<div class="orange"></div>
<div class="cream"></div>
<div class="orange"></div>
<div class="orange"></div>
<div class="cream"></div>
<div class="orange"></div>
<div class="cream"></div>
<style>
  body {
    margin: 0;
    display: flex;
	flex-wrap: wrap;
    background-color: #5C434C;
  }
  div {
    margin: 10px;
    width: 80px;
    height: 80px;
    background: #dd6b4d;
    border-top-left-radius: 80px;
  }
  .orange {
    background-color: #F09462;
  }
  .cream {
    background-color: #F5D6B4;
  }
  
</style>
```

### CSS KATA => [Battle #4. Target #26. Smiley](https://cssbattle.dev/play/26)

```html
<div class="top-line">
	<div class="eyes-outer">
		<div class="eyes-inner"></div>
	</div>
	<div class="eyes-outer">
		<div class="eyes-inner"></div>
	</div>  
</div>

<div class="bottom-line">
  <div class="mouth-outer">
		<div class="mouth-inner happy"></div>
	</div>  
</div>

<style>
  body {
    margin: 0;
    background: #6592CF;
    display: flex;
    flex-direction: column;
  }
  .top-line {
    margin: 40 0 40 0;
    display: flex;
    justify-content: space-evenly;
  }
  .bottom-line {
    margin: 60 0 40 0;
    display: flex;
    justify-content: space-evenly;
  }
  .eyes-outer {
    display: flex;
    justify-content: center;
    align-items: flex-end;
    width: 120px;
    height: 60px;
    margin: 0 40 0 40;
    background: #060F55;
    border-top-left-radius: 120px;
    border-top-right-radius: 120px;
  }
  .eyes-inner {
    width: 80px;
    height: 40px;
    background: #6592CF;
    border-top-left-radius: 80px;
    border-top-right-radius: 80px;
  }
  .mouth-outer {
    display: flex;
    justify-content: center;
    width: 120px;
    height: 60px;
    background: #060F55;
    border-bottom-left-radius: 120px;
    border-bottom-right-radius: 120px;
  }
  .mouth-inner {
    width: 80px;
    height: 40px;
    background: #6592CF;
    border-bottom-left-radius: 80px;
    border-bottom-right-radius: 80px;
  }

</style>
```

### BONUS MID KATA => [Bumps in the Road 7kyu](https://www.codewars.com/kata/57ed30dde7728215300005fa)
### BONUS MID KATA =>[Slaphead 7kyu](https://www.codewars.com/kata/57efab9acba9daa4d1000b30)
### BONUS MID KATA =>[Switcheroo 7kyu](https://www.codewars.com/kata/57f759bb664021a30300007d)
### BONUS MID KATA =>[Valid Spacing 7kyu](https://www.codewars.com/kata/5f77d62851f6bc0033616bd8)