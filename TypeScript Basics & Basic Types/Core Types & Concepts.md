# Core Types & Concepts

## Introduction

There are several core types and concepts that form the foundation of the language. Here's an overview of some key TypeScript concepts and common core types:

## Table of Contents

- [1. **Basic Types:**](#1-basic-types)
    - [a. **`number`:**](#a-number)
    - [b. **`string`:**](#b-string)
    - [c. **`boolean`:**](#c-boolean)
    - [d. **`null` and `undefined`:**](#d-null-and-undefined)
    - [e. **`any`:**](#e-any)
- [2. **Type Annotations:**](#2-type-annotations)
- [3. **Interfaces:**](#3-interfaces)
- [4. **Arrays:**](#4-arrays)
- [5. **Functions:**](#5-functions)
- [6. **Union Types:**](#6-union-types)
- [7. **Literal Types:**](#7-literal-types)
- [8. **Enums:**](#8-enums)
- [9. **Type Aliases:**](#9-type-aliases)
- [10. **Generics:**](#10-generics)

### 1. **Basic Types:**

### a. **`number`:**

Represents both integer and floating-point numbers.

```tsx
let count: number = 42;
```

### b. **`string`:**

Represents textual data.

```tsx
let message: string = "Hello, TypeScript!";
```

### c. **`boolean`:**

Represents a binary choice, `true` or `false`.

```tsx
let isDone: boolean = false;

```

### d. **`null` and `undefined`:**

Represent absence of value.

```tsx
let data: null = null;
let value: undefined = undefined;
```

### e. **`any`:**

Represents a dynamic or unknown type, opting out of static type checking.

```tsx
let dynamicValue: any = 42;
```

### 2. **Type Annotations:**

Type annotations allow you to explicitly specify the type of a variable or function parameter.

```tsx
let age: number = 25;

function greet(name: string): string {
    return `Hello, ${name}!`;
}
```

### 3. **Interfaces:**

Interfaces define contracts for object shapes. They can include properties, methods, and optional members.

```tsx
interface Person {
    name: string;
    age: number;
}

let john: Person = { name: "John", age: 30 };
```

### 4. **Arrays:**

Arrays in TypeScript can be of a specific type or a union of types.

```tsx
let numbers: number[] = [1, 2, 3];
let mixedArray: (number | string)[] = [1, "two", 3];
```

### 5. **Functions:**

Functions can have parameter types and return types.

```tsx
function add(a: number, b: number): number {
    return a + b;
}
```

### 6. **Union Types:**

Union types allow a variable to have one of several types.

```tsx
let result: number | string = 42;
result = "Success";
```

### 7. **Literal Types:**

Literal types allow you to specify exact values as types.

```tsx
let status: "success" | "failure" = "success";
```

### 8. **Enums:**

Enums allow you to define named constant values representing discrete elements or categories.

```tsx
enum Color {
    Red,
    Green,
    Blue,
}

let myColor: Color = Color.Green;
```

### 9. **Type Aliases:**

Type aliases provide a way to create custom names for types, improving code readability.

```tsx
type Point = {
    x: number;
    y: number;
};

let position: Point = { x: 5, y: 10 };
```

### 10. **Generics:**

Generics enable the creation of reusable and flexible components with type parameters.

```tsx
function identity<T>(arg: T): T {
    return arg;
}

let result: string = identity("Hello, TypeScript!");
```

These core types and concepts form the basis of TypeScript's static typing system, providing tools to express the structure and behavior of your code. Understanding and leveraging these concepts is crucial for writing robust and maintainable TypeScript code.