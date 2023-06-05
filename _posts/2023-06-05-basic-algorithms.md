---
  title: Basic Algorithm Scripting 01
  date: 2023-06-05 16:00:00 +0100
categories: [Algorithms, JavaScript]
tags: [algorithms] # TAG names should always be lowercase
author: <author_id>
---

### Reverse a String

```javascript
function reverseString(str) {
  str = str.split("").reverse().join("");
  return str;
}
```

### Factorialize a Number

```javascript
function factorialize(num) {
  if (num === 0 || num === 1) return 1;
  for (let i = num - 1; i >= 1; i--) {
    num *= i;
  }
  return num;
}
```

### Find the Longest Word in a String

```javascript
function findLongestWordLength(str) {
  let result = str;
  result = Math.max(...str.split(" ").map((el) => el.length));
  return result;
}
```

### Return Largest Numbers in Arrays

```javascript
function largestOfFour(arr) {
  arr = arr.map((el) => Math.max(...el));
  return arr;
}

largestOfFour([
  [4, 5, 1, 3],
  [13, 27, 18, 26],
  [32, 35, 37, 39],
  [1000, 1001, 857, 1],
]);
//[ 5, 27, 39, 1001 ]
```

### Confirm the Ending

```javascript
function confirmEnding(str, target) {
  // str = str.endsWith(target)
  let result;
  result = str.substring(str.length - target.length, str.length);
  console.log(result);
  return result === target;
}

confirmEnding("Bastian", "n");
///true
```

### Repeat a String Repeat a String

```javascript
function repeatStringNumTimes(str, num) {
  let result = "";
  if (num > 0) {
    for (let i = 0; i < num; i++) {
      result += str;
    }
  } else {
    return result;
  }
  console.log(result);
  return result;
}

repeatStringNumTimes("abc", 3);
```
