---
title: Sum of the first nth term of Series
date: 2023-06-20 15:00:00 +0100
categories: [Algorithms, JavaScript]
tags: [algorithms] # TAG names should always be lowercase
author: <author_id>
---

```javascript
// my solution
function SeriesSum(n) {
  // for (let s = 0, i = 0; i < n; i++)
  // 조건문 안에 한번에 선언할 수 있음
  let sum = 0;
  for (let i = 0; i < n; i++) {
    sum += 1 / (1 + i * 3);
  }

  return sum.toFixed(2);
}

// recursion
function SeriesSum(n, s = 0) {
  return n ? SeriesSum(n - 1, s + 1 / (3 * n - 2)) : s.toFixed(2);
}
```

> **[toFixed()](https://www.w3schools.com/jsref/jsref_tofixed.asp)**

- converts a number to **a string**
- rounds the string to a specified number of decimals
