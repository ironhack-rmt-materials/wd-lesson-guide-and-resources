# MODULE 1 KATAS

***

## WEEK 1. DAY 3.
### INTRO KATA => [Are You Playing Banjo? 8 kyu](https://www.codewars.com/kata/53af2b8861023f1d88000832/train/javascript)

```javascript
function areYouPlayingBanjo(name) {
  if (name[0].toLowerCase() === "r") {
    return `${name} plays banjo`
  } else {
    return `${name} does not play banjo`
  }
}

// test
console.log( areYouPlayingBanjo("Rutul") )
console.log( areYouPlayingBanjo("Franco") )
```

### INTRO KATA => [Double Char 8 kyu](https://www.codewars.com/kata/56b1f01c247c01db92000076/train/javascript)

```javascript
function doubleChar(str) {
  let myStr = ""
  for (let i = 0; i < str.length; i++) {
    myStr += `${str[i]}${str[i]}`
  }
  return myStr
}

// test
console.log( doubleChar("JavaScript") )
console.log( doubleChar("FTW") )
```

***

## WEEK 1. DAY 5.

### INTRO KATA => [The Feast of Many Beasts 8 kyu](https://www.codewars.com/kata/5aa736a455f906981800360d/train/javascript)

```javascript
function feast(beast, dish) {
  if (beast[0] === dish[0] && beast[beast.length-1] === dish[dish.length-1]) {
    return true
  } else {
    return false
  }
}

// test
console.log( feast("great blue heron", "garlic naan") )
console.log( feast("brown bear", "bear claw") )
```

### INTRO KATA => [Count the Monkeys! 8 kyu](https://www.codewars.com/kata/56f69d9f9400f508fb000ba7/train/javascript)

```javascript
function monkeyCount(n) {
  // for loop and arrays
  let myArr = []
  for (let i = 1; i <= n; i++) {
    myArr.push(i)
  }
  return myArr
}

// test
console.log( monkeyCount(5) ) // [1, 2, 3, 4, 5]
console.log( monkeyCount(3) ) // [1, 2, 3]
```

### EASY Kata => [Remove First and Last Character 8kyu](https://www.codewars.com/kata/56bc28ad5bdaeb48760009b0)

```javascript
function removeChar(str){
  let newStr = str.slice(1, str.length - 1)
  return newStr
};

// one liner
function removeChar(str){
  return str.slice(1, -1)
};

// test
console.log( removeChar('eloquent') ) // 'loquen'
```

***

## WEEK 3. DAY 1.

### EASY Kata => [String repeat 8kyu](https://www.codewars.com/kata/57a0e5c372292dd76d000d7e/javascript)

```javascript
function repeatStr(n, s) {
  let newStr = "";
  for (let i = 0; i < n; i++) {
    newStr += s
  }
  return newStr
}

// one liner with .repeat method
function repeatStr(n, s) {
  return s.repeat(n)
}

// test
console.log( repeatStr(3, "*") ) // "***"
console.log( repeatStr(2, "ha ") ) // "ha ha "
```

### MID Kata => [List Filtering 7kyu](https://www.codewars.com/kata/list-filtering/javascript)

```javascript
function filter_list(l) {
  let newArr = [];
  l.forEach((e) => {
    if (typeof e === "number") {
      newArr.push(e);
    }
  });
  return newArr;
}

// one liner with filter
function filter_list(l) {
  return l.filter(e => typeof e === "number");
}

// test
console.log(filter_list([1, "a", "b", 0, 15])); // [1,0,15]
```

### MID Kata => [Sum of All the multiples 7kyu](https://www.codewars.com/kata/sum-of-all-the-multiples-of-3-or-5/javascript)

```javascript
function findSum(n) {
  let sum = 0;
  for (let i = 1; i <= n; i++) {
    if (i % 3 === 0 || i % 5 === 0) sum += i;
  }
  return sum;
}

// test
console.log( findSum(5) ) //  8
```

### BONUS Kata => [Unique In Order 6 kyu](https://www.codewars.com/kata/54e6533c92449cc251001667/javascript)

```javascript
var uniqueInOrder=function(iterable){
  let newArr = []
  for (let i = 0; i < iterable.length; i++) {
    if (iterable[i] === iterable[i+1]) continue
    newArr.push(iterable[i])
  }
  return newArr
}

// test
console.log( uniqueInOrder('AAAABBBCCDAABBB') ) // ['A','B','C','D','A','B']
```

***

## WEEK 3. DAY 2.

### EASY Kata => [Short Long Short](https://www.codewars.com/kata/50654ddff44f800200000007/train/javascript)

```javascript
function solution(a, b){
  if (a.length < b.length) {
    return `${a}${b}${a}`
  } else {
    return `${b}${a}${b}`
  }
}

// test
console.log( solution('Soon', 'Me') ) // 'MeSoonMe'  
```

### MID Kata => [Vowel Count 7kyu](https://www.codewars.com/kata/vowel-count)

```javascript
function getCount(str) {
  let vowelsCount = 0;
  for (let i = 0; i < str.length; i++) {
    if (str[i] === "a" || str[i] === "e" || str[i] === "i" || str[i] === "o" || str[i] === "u") {
      vowelsCount++;
    }
  }
  return vowelsCount;
}

// using switch
function getCount(str) {
  let vowelsCount = 0;
  for (let i = 0; i < str.length; i++) {
    switch (str[i]) {
      case "a":
      case "e":
      case "i":
      case "o":
      case "u":
        vowelsCount++;
    }
  }
  return vowelsCount;
}

// using regex
function getCount(str) {
  let vowelsCount = 0;
  const regex = /^[aeiou]$/i;
  for (let i = 0; i < str.length; i++) {
    if (regex.test(str[i])) vowelsCount++;
  }
  return vowelsCount;
}

// test
console.log( getCount("abracadabra") ) // 5
```

### HARD Kata => [Find The Parity Outlier 6kyu](https://www.codewars.com/kata/5526fc09a1bbd946250002dc)

```javascript
function findOutlier(integers) {
  let evenArr = [], oddArr = [];
  integers.forEach(e => {
    if (e % 2 === 0) evenArr.push(e);
    else oddArr.push(e);
  });
  if (evenArr.length === 1) return evenArr[0];
  else return oddArr[0];
}

// using ternaries
function findOutlier(integers) {
  let evenArr = [], oddArr = [];
  integers.forEach(e => e % 2 === 0 ? evenArr.push(e) : oddArr.push(e));
  return evenArr.length === 1 ? evenArr[0] : oddArr[0];
}

// test
console.log( findOutlier([2, 6, 8, 10, 3]) ); // 3
```

***

##  WEEK 3. DAY 3.

### EASY Kata => [Reversed Strings 8kyu](https://www.codewars.com/kata/5168bb5dfe9a00b126000018)

```javascript
function solution(str){
  let newStr = "";
  for (let i = str.length-1; i >= 0 ; i--) {
    newStr += str[i]
  }
  return newStr
}

// one liner but not the best performance wise
function solution(str){
  return str.split("").reverse().join("")
}

// test
console.log( solution('world') ) // 'dlrow'
```

### MID Kata => [Credit Card Mask 7kyu](https://www.codewars.com/kata/credit-card-mask/javascript)

```javascript
function maskify(cc) {
  if (cc.length > 4) {
    let hashtagStr = "#";
    return hashtagStr.repeat(cc.length - 4) + cc.slice(cc.length - 4);
  } else {
    return cc;
  }
}

// one line
function maskify2(cc) {
  return cc.length > 4
    ? "#".repeat(cc.length - 4) + cc.slice(cc.length - 4)
    : cc;
}

// test
console.log(maskify("4556364607935616"));
// '############5616'
```

### MID Kata => [Inverting a Hash 7kyu](https://www.codewars.com/kata/inverting-a-hash/train/javascript)

```javascript
function invertHash(hash) {
  let keys = Object.keys(hash);
  let values = Object.values(hash);
  let newObj = {};
  for (let i = 0; i < keys.length; i++) {
    newObj[values[i]] = keys[i];
  }
  return newObj;
}

// with for in loop
function invertHash(hash) {
  let newObj = {};
  for (let key in hash) {
    let value = hash[key]
    newObj[value] = key
  }
  return newObj
}

// test
console.log( invertHash({ a: '1', b: '2', c: '3' }) )
// { 1: 'a', 2: 'b', 3: 'c' }
```

***

## WEEK 3. DAY 4. 

### MID Kata (OPTIONAL) => [Square Every Digit 7kyu](https://www.codewars.com/kata/square-every-digit/train/javascript)

```javascript
function squareDigits(num) {
  let numStr = num.toString()
  let newNum = ""
  for (let i = 0; i < numStr.length; i++) {
    newNum += Number(numStr[i]) ** 2
  }
  return Number(newNum)
}

// one liner with .reduce
function squareDigits(num) {
  return Number(num.toString().split("").reduce((a, e) => a + e ** 2, ""));
}

// test
console.log( squareDigits(9119) ); // 811181
```

### MID Kata (OPTIONAL) => [Isograms 7kyu](https://www.codewars.com/kata/54ba84be607a92aa900000f1)

```javascript
function isIsogram(str) {
  let check = true;
  str = str.toLowerCase();

  for (let i = 0; i < str.length; i++) {
    const letter = str[i];
    const wordWithoutLetter = str.slice(0, i) + str.slice(i + 1);
    if (wordWithoutLetter.includes(letter)) {
      check = false;
      break;
    }
  }

  return check;
}
```

### HARD Kata (OPTIONAL) => [Playing with digits 6kyu](https://www.codewars.com/kata/playing-with-digits/train/javascript)

```javascript
function digPow(n, p) {
  let sum = 0;
  let numberStr = n.toString();
  for (let i = 0; i < numberStr.length; i++) {
    let num = parseInt(numberStr[i]);
    sum += num ** p;
    p++;
  }
  let k = sum / n;
  return Number.isInteger(k) ? k : -1;
}

// test
console.log(digPow(89, 1)); // 1
console.log(digPow(46288, 3)); // 51
// 46288 --> 4³ + 6⁴+ 2⁵ + 8⁶ + 8⁷ = 2360688 = 46288 * 51
//   n       n**p + n**(p+1) ...      sum       n     k
```

***