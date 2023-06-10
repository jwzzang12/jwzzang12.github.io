---
title: Complementary DNA
date: 2023-06-10 14:30:00 +0100
categories: [Algorithms, JavaScript]
tags: [algorithms] # TAG names should always be lowercase
author: <author_id>
---

> **[JavaScript RegExp g Modifier](https://www.w3schools.com/jsref/jsref_regexp_g.asp)**

#### Syntax

```javascript
new RegExp("regexp", "g")

or simply:

/regexp/g
```

The "g" modifier specifies a global match.
A global match finds all matches (compared to only the first).

```javascript
// solution
let pairs = { A: "T", T: "A", C: "G", G: "C" };
const DNAStrand = (dna) => dna.replace(/./g, (c) => pairs[c]);
console.log(pairs["A"]); // T
```
