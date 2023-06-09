---
title: Odd or Even?
date: 2023-06-09 13:15:00 +0100
categories: [Algorithms, JavaScript]
tags: [algorithms] # TAG names should always be lowercase
author: <author_id>
---

```javascript
// my solution
function oddOrEven(array) {
  if (array === [0] || array.length === 0) return "even";
  return array.reduce((a, b) => a + b) % 2 === 0 ? "even" : "odd";
}

// set initial value reduces code
// 0 casts to false and 1 casts true
function oddOrEven(arr) {
  return arr.reduce((a, b) => a + b, 0) % 2 ? "odd" : "even";
}
```
