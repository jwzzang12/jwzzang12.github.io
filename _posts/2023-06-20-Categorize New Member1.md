---
title: Categorize New Member
date: 2023-06-20 15:30:00 +0100
categories: [Algorithms, JavaScript]
tags: [algorithms] # TAG names should always be lowercase
author: <author_id>
---

```javascript
// my solution
function openOrSenior(data) {
  return data.map((el) => (el[0] >= 55 && el[1] > 7 ? "Senior" : "Open"));
}

// destructuring looks better
function openOrSenior(data) {
  return data.map(([age, handicap]) =>
    age >= 55 && handicap > 7 ? "Senior" : "Open"
  );
}
```
