---
title: Printer Errors
date: 2023-06-15 20:30:00 +0100
categories: [Algorithms, JavaScript]
tags: [algorithms] # TAG names should always be lowercase
author: <author_id>
---

```javascript
// my solution
function printerError(s) {
  let error = /[n-z]/g;
  let count = 0;
  for (let i = 0; i < s.length; i++) {
    if (s[i].match(error)) {
      count++;
    }
  }
  return `${count}/${s.length}`;
}

// other
function printerError(s) {
  var count = 0;
  for (var i = 0; i < s.length; i++) {
    if (s[i] > "m") {
      count++;
    }
  }
  return count + "/" + s.length;
}
```

> ```
> console.log("m" < "n");
> // true
> ```
