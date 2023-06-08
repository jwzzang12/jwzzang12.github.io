---
title: Exes and Ohs
date: 2023-06-08 16:30:00 +0100
categories: [Algorithms, JavaScript]
tags: [algorithms] # TAG names should always be lowercase
author: <author_id>
---

### Exes and Ohs

```javascript
// my solution
function XO(str) {
  const arr = str.toLowerCase().split("");
  let oNum = 0;
  let xNum = 0;
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] === "o") {
      oNum++;
    } else if (arr[i] === "x") {
      xNum++;
    }
  }
  return oNum === xNum;
}

// simple solution
function XO(str) {
  str = str.toLowerCase().split("");
  return (
    str.filter((x) => x === "x").length === str.filter((x) => x === "o").length
  );
}
```
