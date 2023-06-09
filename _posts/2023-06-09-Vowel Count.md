---
title: Vowel Count
date: 2023-06-09 12:30:00 +0100
categories: [Algorithms, JavaScript]
tags: [algorithms] # TAG names should always be lowercase
author: <author_id>
---

```javascript
// my solution
function getCount(str) {
  const vowel = str
    .split("")
    .filter(
      (el) => el === "a" || el === "e" || el === "i" || el === "o" || el === "u"
    );
  return vowel.length;
}

// soultion 1
function getCount(str) {
  return (str.match(/[aeiou]/gi) || []).length;
}

// solution 2
function getCount(str) {
  const vowels = ["a", "e", "i", "o", "u"];
  let vowelsCount = 0;

  for (let i of str) {
    if (vowels.includes(i)) vowelsCount++;
  }

  return vowelsCount;
}
```
