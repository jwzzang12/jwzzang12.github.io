---
title: Call Signature
date: 2023-07-24 11:00:00 +0100
categories: [Coding, TypeScript]
tags: [typescript] # TAG names should always be lowercase
author: <author_id>
---

# Call Signature

```tsx
type Add = (a: number, b: number) => number;

const add: Add = (a, b) => a + b;
```

- the type signature of a function or method when defining its parameters and return type

## Overloading

- the function has multiple call signatures

polymorphism

overloading

generics

## Polymorphism

```tsx
type SuperPrint = {
  <T>(arr: T[]): T;
};

const superPrint: SuperPrint = (arr) => arr[0];

//or

function superPrint<T>(a: T[]) {
  return a[0];
}

const a = superPrint([1, 2, 3]);
const b = superPrint([true, false, true]);
const c = superPrint(["a", "b"]);
const d = superPrint([1, 2, "a", "b", true]);

//typescript infers types
```
