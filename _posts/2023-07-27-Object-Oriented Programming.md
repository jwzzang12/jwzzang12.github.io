---
title: Object-Oriented Programming
date: 2023-07-27 11:00:00 +0100
categories: [Coding, TypeScript]
tags: [typescript] # TAG names should always be lowercase
author: <author_id>
---

# Object-Oriented Programming

```tsx
class Player {
  constructor(
    private firstName: string,
    private lastName: string,
    public nickName: string
  ) {}
}

const son = new Player("Heungmin", "Son", "Sonny");
//not working
son.firstName;

//working!
son.nickName;
```

## Abstract Class

- A class that cannot be instantiated directly (you cannot create objects directly from an abstract class)

### **Abstract Methods**

- Abstract classes can contain abstract methods, which are declared without implementation details.

### **Extending Abstract Classes**

- To create a subclass that extends an abstract class, you use the **`extends`** keyword, and you must provide implementations for all the abstract methods.

### `public` , `protected` and `private`

- Access modifiers that control the visibility and accessibility of class members (properties and methods)

1. **`public`**:
   - The default access modifier
   - Public members can be accessed from anywhere, both within the class and outside the class
2. **`protected`**:
   - Members marked as `protected` are accessible within the class and its subclasses (i.e., child classes)
   - They are not accessible from instances of the class directly (outside the class), but they can be accessed by subclasses of that class
   - This access level allows for sharing certain members with child classes while still restricting access from outside
3. **`private`**:
   - Members marked as `private` are accessible only within the class itself
   - They are not accessible from outside the class, including its subclasses. Only the class itself can access its private members

```tsx
class Person {
  public name: string; // Public member accessible from anywhere
  protected age: number; // Protected member accessible within the class and subclasses
  private gender: string; // Private member accessible only within the class

  constructor(name: string, age: number, gender: string) {
    this.name = name;
    this.age = age;
    this.gender = gender;
  }

  public getGender(): string {
    return this.gender; // Private member accessed within the class through a public method
  }
}

class Employee extends Person {
  private employeeId: number;

  constructor(name: string, age: number, gender: string, employeeId: number) {
    super(name, age, gender);
    this.employeeId = employeeId;
  }

  public getInfo(): string {
    return `${this.name}, ${this.age} years old, Employee ID: ${this.employeeId}`;
  }

  public getAge(): number {
    return this.age; // Protected member accessed within a subclass
  }
}

const person = new Person("John", 30, "Male");
console.log(person.name); // Accessible (public)
console.log(person.age); // Error: 'age' is protected and only accessible within the class and its subclasses
console.log(person.gender); // Error: 'gender' is private and not accessible from outside the class
console.log(person.getGender()); // Accessible (through a public method)

const employee = new Employee("Alice", 25, "Female", 12345);
console.log(employee.getInfo()); // Accessible (public)
console.log(employee.getAge()); // Accessible (protected through a subclass)
```
