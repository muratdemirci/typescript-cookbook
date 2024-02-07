# Object Types

## Introduction

Object types allow you to define the shape of objects by specifying the types of their properties. There are several ways to define object types, and we'll explore the most common approaches:

## Table of Contents

- [1. **Object Literal:**](#1-object-literal)
- [2. **Interface:**](#2-interface)
- [3. **Optional Properties:**](#3-optional-properties)
- [4. **Readonly Properties:**](#4-readonly-properties)
- [5. **Index Signatures:**](#5-index-signatures)
- [6. **Extending Interfaces:**](#6-extending-interfaces)
- [7. **Intersection Types:**](#7-intersection-types)
- [8. **Type Aliases:**](#8-type-aliases)

### 1. **Object Literal:**

You can directly specify the types of properties in an object literal.

```tsx
let person: { name: string; age: number } = { name: "John", age: 30 };
```

### 2. **Interface:**

Interfaces are a powerful way to define object types and provide a clear contract for the expected structure of an object.

```tsx
interface Person {
    name: string;
    age: number;
}

let employee: Person = { name: "Alice", age: 25 };
```

### 3. **Optional Properties:**

You can mark properties as optional using the `?` syntax.

```tsx
interface Car {
    brand: string;
    model?: string; // Optional property
}

let myCar: Car = { brand: "Toyota" };
```

### 4. **Readonly Properties:**

You can mark properties as readonly using the `readonly` keyword.

```tsx
interface Point {
    readonly x: number;
    readonly y: number;
}

let coordinates: Point = { x: 1, y: 2 };
// coordinates.x = 3; // Error: Cannot assign to 'x' because it is a read-only property.
```

### 5. **Index Signatures:**

You can use index signatures to define objects with dynamic keys.

```tsx
interface Dictionary {
    [key: string]: number;
}

let ages: Dictionary = {
    "John": 30,
    "Alice": 25,
};
```

### 6. **Extending Interfaces:**

Interfaces can extend other interfaces, allowing you to build on existing definitions.

```tsx
interface Shape {
    color: string;
}

interface Square extends Shape {
    sideLength: number;
}

let mySquare: Square = { color: "red", sideLength: 5 };
```

### 7. **Intersection Types:**

You can combine multiple types using intersection types (`&`).

```tsx
type Name = { firstName: string };
type Age = { age: number };

let personInfo: Name & Age = { firstName: "John", age: 30 };
```

### 8. **Type Aliases:**

You can use type aliases to create reusable object types.

```tsx
type Coordinates = { x: number; y: number };

let point: Coordinates = { x: 1, y: 2 };
```

These are some common ways to define object types in TypeScript. Choosing the right approach depends on the specific requirements of your application and the level of abstraction you want to achieve. Using interfaces is a recommended practice for defining object types in TypeScript because of their expressiveness and the ability to extend and reuse them.