# Working with Numbers, Strings & Booleans

## Introduction

Working with numbers, strings, and booleans is similar to JavaScript, but TypeScript allows you to define types explicitly. Here are some examples:

## Table of Contents 

- [1. **Numbers:**](#1-numbers)
- [2. **Strings:**](#2-strings)
- [3. **Booleans:**](#3-booleans)
- [4. **Type Annotations for Function Parameters and Return Types:**](#4-type-annotations-for-function-parameters-and-return-types)
- [5. **Type Inference in Functions:**](#5-type-inference-in-functions)
- [6. **Type Assertion:**](#6-type-assertion)

### 1. **Numbers:**

```tsx
// Explicitly defining the type
let age: number = 25;

// Operations with numbers
let sum: number = 10 + 5;
let product: number = 3 * 4;

// Type inference
let height = 180; // TypeScript infers the type as number
```

### 2. **Strings:**

```tsx
// Explicitly defining the type
let message: string = "Hello, TypeScript!";

// Concatenation
let greeting: string = "Hi";
let name: string = "Alice";
let fullMessage: string = greeting + ", " + name;

// Template literals
let templateMessage: string = `Hello, ${name}!`;
```

### 3. **Booleans:**

```tsx
// Explicitly defining the type
let isValid: boolean = true;

// Conditional statements
if (isValid) {
    console.log("It's valid.");
} else {
    console.log("It's not valid.");
}

// Type inference
let isTrue = false; // TypeScript infers the type as boolean
```

### 4. **Type Annotations for Function Parameters and Return Types:**

```tsx
// Function with number parameters and return type
function addNumbers(x: number, y: number): number {
    return x + y;
}

// Function with string parameters and return type
function concatenateStrings(str1: string, str2: string): string {
    return str1 + str2;
}

// Function with boolean parameters and return type
function isAdult(age: number): boolean {
    return age >= 18;
}
```

### 5. **Type Inference in Functions:**

```tsx
// TypeScript infers the parameter and return types
function multiply(x: number, y: number) {
    return x * y;
}
let result: number = multiply(3, 4); // result is inferred as number
```

### 6. **Type Assertion:**

```tsx
// Type assertion for variables
let strLength: number = (<string>"Hello").length;

// Type assertion for values
let value: any = "World";
let valueLength: number = (value as string).length;
```

It's important to note that TypeScript provides the benefit of static typing, allowing you to catch potential errors during development. Explicitly defining types helps improve code readability and maintainability. The examples above demonstrate how to work with numbers, strings, and booleans while leveraging TypeScript's type system.