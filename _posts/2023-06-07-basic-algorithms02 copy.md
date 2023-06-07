---
title: TypeScript Fundamental
date: 2023-06-07 23:00:00 +0100
categories: [Coding, TypeScript]
tags: [typeScript] # TAG names should always be lowercase
author: <author_id>
---

- Primitives : number, string, boolean
- More complex types: arrays, objects
- Function types. parameters

#### Primitives

```typescript
let age: number;

age = 12;

let userName: string;

userName = "Moon";

let isTrue: boolean;

isTrue = true;
```

#### More complex types

```typescript
let hobbies: string[];
// arrary of string

hobbies = ["Sports", "Drawing", "Reading"]

let person: {
  name: string;
  age: number;
};
//object type definition

person = {
  name: "rabbit";
  age: 2023;
}

let people: {
  name: string;
  age: number;
}[];
//array of objects
```

#### Type inference (타입추론)

```typescript
let course = "React";
course = 12341; //error
```

#### union type

```typescript
let course: string | number | boolean = "React";
course = 12341; //no error
```

more flexible

#### Type Alias

```typescript
//type definition
type Person = {
  name: string;
  age: number;
};

let people: Person[];
```

make code precise, simple

#### Functions & types

```typescript
function add(a: number, b: number) {
  return a + b;
}
//refered from return value type (as number)

function result(value: any) {
  console.log(value);
}
//return type: void
```

#### Generics

```typescript
function insertAtBeginning<T>(array: T[], value: T) {
  const newArray = [value, ...array];
  return newArray;
}

const demo = [1, 2, 3];
const numberArray = insertAtBeginning(demo, -1); //[-1, 1, 2, 3]
const stringArray = insertAtBeginning(["a", "b", "c"], "d");
//type safe yet flexible
```
