# Understanding Types

## Introduction

Understanding types in TypeScript is fundamental to leveraging the language's static typing features. TypeScript provides a way to describe the shape and behavior of values, making it more robust and maintainable. Let's explore key concepts related to types in TypeScript:

## Table of Contents

- [1. **Basic Types:**](#1-basic-types)
  - [a. **Number:**](#a-number)
  - [b. **String:**](#b-string)
  - [c. **Boolean:**](#c-boolean)
  - [d. **Array:**](#d-array)
- [2. **Object Types:**](#2-object-types)
  - [a. **Object Literal:**](#a-object-literal)
  - [b. **Interface:**](#b-interface)
- [3. **Union and Intersection Types:**](#3-union-and-intersection-types)
  - [a. **Union Types:**](#a-union-types)
  - [b. **Intersection Types:**](#b-intersection-types)
- [4. **Function Types:**](#4-function-types)
  - [a. **Function Parameter and Return Types:**](#a-function-parameter-and-return-types)
- [5. **Generics:**](#5-generics)
  - [a. **Generic Function:**](#a-generic-function)
- [6. **Type Aliases:**](#6-type-aliases)
  - [a. **Creating Custom Types:**](#a-creating-custom-types)
- [7. **Type Assertion:**](#7-type-assertion)
  - [a. **Explicit Type Conversion:**](#a-explicit-type-conversion)
- [8. **Declaration Files (.d.ts):**](#8-declaration-files-dts)
  - [a. **Defining Types for External Modules:**](#a-defining-types-for-external-modules)

### 1. **Basic Types:**

### a. **Number:**

```tsx
let age: number = 25;
```

### b. **String:**

```tsx
let name: string = "Alice";
```

### c. **Boolean:**

```tsx
let isValid: boolean = true;
```

### d. **Array:**

```tsx
let numbers: number[] = [1, 2, 3];
```

### 2. **Object Types:**

### a. **Object Literal:**

```tsx
let person: { name: string; age: number } = { name: "John", age: 30 };
```

### b. **Interface:**

```tsx
interface Person {
    name: string;
    age: number;
}

let employee: Person = { name: "Alice", age: 25 };
```

### 3. **Union and Intersection Types:**

### a. **Union Types:**

```tsx
let result: number | string = 10;
result = "Success";
```

### b. **Intersection Types:**

```tsx
type Name = { firstName: string };
type Age = { age: number };

let personInfo: Name & Age = { firstName: "John", age: 30 };
```

### 4. **Function Types:**

### a. **Function Parameter and Return Types:**

```tsx
function add(x: number, y: number): number {
    return x + y;
}
```

### 5. **Generics:**

### a. **Generic Function:**

```tsx
function identity<T>(value: T): T {
    return value;
}

let result: number = identity(10);
```

### 6. **Type Aliases:**

### a. **Creating Custom Types:**

```tsx
type Point = { x: number; y: number };

let coordinates: Point = { x: 1, y: 2 };
```

### 7. **Type Assertion:**

### a. **Explicit Type Conversion:**

```tsx
let strLength: number = (<string>"Hello").length;
```

### 8. **Declaration Files (.d.ts):**

### a. **Defining Types for External Modules:**

```tsx
// example.d.ts
declare module "example-library" {
    function myFunction(value: string): number;
}
```

Understanding these types and concepts allows you to create more expressive and error-resistant TypeScript code. TypeScript's static typing helps catch potential issues during development, making your codebase more robust and maintainable. Choose the appropriate type based on the context and requirements of your code.