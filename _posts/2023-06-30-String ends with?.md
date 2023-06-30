---
title: String ends with?
date: 2023-06-30 14:30:00 +0100
categories: [Algorithms, JavaScript]
tags: [algorithms] # TAG names should always be lowercase
author: <author_id>
---

```javascript
// soultion
function solution(str, ending) {
  return str.endsWith(ending);
}

// my solution
function solution(str, ending) {
  const leng = ending.length;
  if (leng === 0) return true;
  return str.slice(-leng) === ending;
}
```

> **[String.prototype.endsWith()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/endsWith)**
>
> The endsWith() method determines whether a string ends with the characters of a specified string, returning true or false as appropriate.
