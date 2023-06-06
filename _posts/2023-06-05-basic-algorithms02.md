---
  title: Basic Algorithm Scripting 02
  date: 2023-06-06 16:00:00 +0100
categories: [Algorithms, JavaScript]
tags: [algorithms] # TAG names should always be lowercase
author: <author_id>
---

### Truncate a String

```javascript
function truncateString(str, num) {
  if (num >= str.length) {
    return str;
  } else {
    return str.slice(0, num) + "...";
  }
}

truncateString("A-tisket a-tasket A green and yellow basket", 8);
```

### Finders Keepers

```javascript
function findElement(arr, func) {
  return arr.find(func);
}

findElement([1, 2, 3, 4], function (num) {
  return num % 2 === 0;
});
```

> **Array.prototype.find()**
> The find() method returns the first element in the provided array that satisfies the provided testing function. If no values satisfy the testing function, undefined is returned.

### Boo who

```javascript
function booWho(bool) {
  return typeof bool === "boolean";
}

booWho(null);
```

### Title Case a Sentence

```javascript
function titleCase(str) {
  let result = str
    .toLowerCase()
    .split(" ")
    .map((el) => el[0].toUpperCase() + el.slice(1))
    .join(" ");
  return result;
}

titleCase("I'm a little tea pot");
```

### Slice and Splice

```javascript
// soultion 1
function frankenSplice(arr1, arr2, n) {
  let localArray = arr2.slice();
  for (let i = 0; i < arr1.length; i++) {
    localArray.splice(n, 0, arr1[i]);
    n++;
  }
  return localArray;
}

// soultion 2
function frankenSplice(arr1, arr2, n) {
  let localArr = arr2.slice();
  localArr.splice(n, 0, ...arr1);
  return localArr;
}
```

### Falsy Bouncer

```javascript
function bouncer(arr) {
  let result = arr.filter((el) => Boolean(el) === true);
  // return arr.filter(Boolean);
  return result;
}

bouncer([7, "ate", "", false, 9]);
```

### Where do I Belong

```javascript
function getIndexToIns(arr, num) {
  arr.sort((a, b) => a - b);
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] >= num) return i;
  }
  return arr.length;
}

getIndexToIns([40, 60], 50);
```

### Mutations

```javascript
function mutation([target, test], i = 0) {
  target = target.toLowerCase();
  test = test.toLowerCase();
  return i >= test.length
    ? true
    : !target.includes(test[i])
    ? false
    : mutation([target, test], i + 1);
}
```

### Chunky Monkey

```javascript
//solution 1
function chunkArrayInGroups(arr, size) {
  const chunkyArr = [];
  for (let i = 0; i < arr.length; i += size) {
    chunkyArr.push(arr.slice(i, i + size));
  }
  return chunkyArr;
}

chunkArrayInGroups(["a", "b", "c", "d"], 2);

//solution 2
function chunkArrayInGroups(arr, size) {
  const chunkyArr = [];
  while (arr.length > 0) {
    chunkyArr.push(arr.splice(0, size));
  }
  return chunkyArr;
}
```
