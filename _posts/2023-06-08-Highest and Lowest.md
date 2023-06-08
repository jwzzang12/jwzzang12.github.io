---
title: Highest and Lowest
date: 2023-06-08 15:30:00 +0100
categories: [Algorithms, JavaScript]
tags: [algorithms] # TAG names should always be lowercase
author: <author_id>
---

### Highest and Lowest

```javascript
// soultion 1
function highAndLow(numbers) {
  const result = numbers
    .split(" ")
    .map((el) => parseInt(el))
    .sort((a, b) => b - a);
  if (result.length === 1) {
    return result + " " + result;
  }
  return result.shift() + " " + result.pop();
}

// soultion 2
function highAndLow(numbers) {
  numbers = numbers.split(" ");
  return `${Math.max(...numbers)} ${Math.min(...numbers)}`;
}
```
