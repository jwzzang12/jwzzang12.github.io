---
title: Find the odd int
date: 2023-07-11 11:00:00 +0100
categories: [Algorithms, JavaScript]
tags: [algorithms] # TAG names should always be lowercase
author: <author_id>
---

**Description**

Given an array of integers, find the one that appears an odd number of times.

There will always be only one integer that appears an odd number of times.

Examples

[7] should return 7, because it occurs 1 time (which is odd).
[0] should return 0, because it occurs 1 time (which is odd).
[1,1,2] should return 2, because it occurs 1 time (which is odd).
[0,1,0,1,0] should return 0, because it occurs 3 times (which is odd).
[1,2,2,3,3,3,4,3,3,3,2,2,1] should return 4, because it appears 1 time (which is odd).

```javascript
// soultion
const findOdd = (A) => A.reduce((a, b) => a ^ b);
// if there are same values, it became 0 eventually
// only one of odd value survive:>
```

### [Bitwise XOR (^)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_XOR)

if input values are same : return 0
if input values are not same : return 1

> 0 XOR 0 = 0
> 0 XOR 1 = 1
> 1 XOR 0 = 1
> 1 XOR 1 = 0

example

> let a = 5; // 0101
> a ^= 3; // 0011
> console.log(a); // 0110
> // expected output: 6
