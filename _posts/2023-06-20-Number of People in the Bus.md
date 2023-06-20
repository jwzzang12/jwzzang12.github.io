---
title: Number of People in the Bus
date: 2023-06-20 16:00:00 +0100
categories: [Algorithms, JavaScript]
tags: [algorithms] # TAG names should always be lowercase
author: <author_id>
---

```javascript
// my solution
const number = function (busStops) {
  let ppl = 0;

  busStops.map(([on, off]) => {
    ppl += on - off;
  });

  return ppl;
};

// using reduce method
const number = (busStops) =>
  busStops.reduce((ppl, [on, off]) => ppl + on - off, 0);
```

> **[Array.reduce()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)**

#### Syntax

reduce(callbackFn, initialValue)

```javascript
const arr = [1, 2, 3, 4];

// 0 + 1 + 2 + 3 + 4
const initialValue = 0;
const sumWithInitial = arr.reduce(
  (accumulator, currentValue) => accumulator + currentValue,
  initialValue
);

console.log(sumWithInitial);
// Expected output: 10
```
