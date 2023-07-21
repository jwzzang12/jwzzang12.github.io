---
title: Types of TypeScript 2
date: 2023-07-21 06:00:00 +0100
categories: [Coding, TypeScript]
tags: [typescript] # TAG names should always be lowercase
author: <author_id>
---

- Optional parameter ?

```tsx
const player: {
  name: string;
  age?: number;
} = {
  name: 'son',
};

if (player.age > 20) {
} //error

// check the possibility of player.age being undefined
if (**player.age** && player.age > 20) {
}
```

### More about **Type Alias**

```tsx
type Player = {
  name: string;
  age?: number;
};

const player1: Player = {
  name: "son",
};
const player2: Player = {
  name: "kane",
};

// specify return type of function
function playerMaker1(name: string): Player {
  return {
    name,
  };
}
// array function version
const playerMaker2 = (name: string): Player => ({ name });

const son = playerMaker1("son");
son.age = 31;
```

### readonly

- make a property or array immutable or read-only
- When a property is marked as **`readonly`**, it means that its value cannot be modified once it is assigned

### Tuple

- a data structure that allows you to store a fixed number of elements of different types
- a specific type definition for each element position

```tsx
let player: [string, number, boolean];

player = ["Son", 31, true];
```

### Any

- **`any`** type is a flexible type that represents values of any type
- it behaves like a regular JavaScript
- disables TypeScript’s protection
