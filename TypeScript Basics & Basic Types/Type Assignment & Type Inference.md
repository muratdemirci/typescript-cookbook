# Type Assignment & Type Inference

## Introduction

Type assignment and type inference play crucial roles in defining and working with variables. Let's explore both concepts:

## Table of Contents

- [1. Type Assignment:](#1-type-assignment)
- [Example:](#example)
- [2. Type Inference:](#2-type-inference)
- [Example:](#example-1)
- [3. Combining Type Assignment and Type Inference:](#3-combining-type-assignment-and-type-inference)
- [Example:](#example-2)
- [4. Function Parameter and Return Type Annotations:](#4-function-parameter-and-return-type-annotations)
- [Example:](#example-3)

### 1. Type Assignment:

Type assignment involves explicitly specifying the type of a variable. This is done using a colon (`:`) followed by the type name.

### Example:

```tsx
// Type assignment for numbers
let age: number = 25;

// Type assignment for strings
let name: string = "Alice";

// Type assignment for booleans
let isValid: boolean = true;

// Type assignment for arrays
let numbers: number[] = [1, 2, 3];
```

### 2. Type Inference:

Type inference is a TypeScript feature that automatically determines the type of a variable based on its initialization. When a variable is assigned a value during declaration, TypeScript infers its type without explicit type annotations.

### Example:

```tsx
// Type inference for numbers
let height = 180; // TypeScript infers the type as number

// Type inference for strings
let greeting = "Hello"; // TypeScript infers the type as string

// Type inference for booleans
let isTrue = false; // TypeScript infers the type as boolean

// Type inference for arrays
let fruits = ["apple", "orange", "banana"]; // TypeScript infers the type as string[]
```

Type inference simplifies code by reducing the need for explicit type annotations. However, explicit type annotations can still be beneficial for clarity and documentation.

### 3. Combining Type Assignment and Type Inference:

In many cases, you might use a combination of type assignment and type inference.

### Example:

```tsx
// Type assignment with type inference
let employeeId: number = 123;
let employeeName = "John Doe"; // TypeScript infers the type as string

// Type assignment with complex types
let userDetails: { id: number; name: string } = {
    id: employeeId,
    name: employeeName,
};
```

### 4. Function Parameter and Return Type Annotations:

Type assignment is commonly used when defining function parameter types and return types.

### Example:

```tsx
// Function with type annotations
function addNumbers(x: number, y: number): number {
    return x + y;
}

// Type inference for function return type
function multiply(x: number, y: number) {
    return x * y; // TypeScript infers the return type as number
}
```

Both type assignment and type inference contribute to the language's static typing features, helping catch potential errors during development and providing better tooling support. Choose the approach that fits the context of your code and enhances readability.