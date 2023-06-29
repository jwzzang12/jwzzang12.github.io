---
title: Disemvowel Trolls
date: 2023-06-30 00:00:00 +0100
categories: [Algorithms, JavaScript]
tags: [algorithms] # TAG names should always be lowercase
author: <author_id>
---

```javascript
// my solution
function disemvowel(str) {
  const vowel = /[aioueAIOUE]/g;
  return str.replace(vowel, "");
}
```

```javascript
//add i = not care about upper/lowercase
const vowel = /[aioue]/gi;
```
