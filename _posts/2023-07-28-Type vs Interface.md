---
title: Type vs Interface
date: 2023-07-28 14:30:00 +0100
categories: [Coding, TypeScript]
tags: [typescript] # TAG names should always be lowercase
author: <author_id>
---

# Type vs Interface

## Interface

- A structure that defines the shape or contract for an object

```tsx
// type
type PlayerA = {
  name: string;
};
type PlayerAA = PlayerA & {
  number: number;
};
const playerA: PlayerAA = {
  name: "Son",
  number: 7,
};

// interface
interface PlayerB {
  name: string;
}
interface PlayerBB extends PlayerB {
  number: number;
}
//possible to add property under same interface name
interface PlayerBB {
  team: string;
}
const player: PlayerBB = {
  name: "Son",
  number: 7,
  team: "TOT",
};
```
