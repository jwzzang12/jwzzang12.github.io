---
title: Jaden Casing Strings
date: 2023-06-10 15:00:00 +0100
categories: [Algorithms, JavaScript]
tags: [algorithms] # TAG names should always be lowercase
author: <author_id>
---

```javascript
// my solution
String.prototype.toJadenCase = function () {
  const wordArr = this.split(" ");
  // change first character into uppercase
  return wordArr
    .map((el) => (el = el[0].toUpperCase() + el.slice(1)))
    .join(" ");
};
```
