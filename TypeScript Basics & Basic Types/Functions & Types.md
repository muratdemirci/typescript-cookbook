# Functions & Types

## Introduction

Functions are first-class citizens, and you can define types for functions to provide clear interfaces and enforce type safety. Here's an overview of how functions and types are used together in TypeScript:

## Table of Contents

- [1. **Function Declarations:**](#1-function-declarations)
- [2. **Function Expressions:**](#2-function-expressions)
- [3. **Function Types:**](#3-function-types)
- [4. **Optional and Default Parameters:**](#4-optional-and-default-parameters)
- [5. **Rest Parameters:**](#5-rest-parameters)
- [6. **Function Types as Parameters:**](#6-function-types-as-parameters)
- [7. **Generic Functions:**](#7-generic-functions)
- [8. **Function Overloads:**](#8-function-overloads)
- [9. **Callbacks:**](#9-callbacks)

### 1. **Function Declarations:**

You can declare functions with type annotations for parameters and return types:

```tsx
function add(a: number, b: number): number {
    return a + b;
}
```

In this example, the `add` function takes two parameters (`a` and `b`) of type `number` and returns a value of type `number`.

### 2. **Function Expressions:**

Functions can also be assigned to variables and used as expressions:

```tsx
const subtract: (a: number, b: number) => number = function (a, b) {
    return a - b;
};
```

Here, the `subtract` variable is assigned a function expression with a specified type for parameters and return value.

### 3. **Function Types:**

You can define function types separately using the `type` keyword:

```tsx
type MathOperation = (a: number, b: number) => number;
```

Now, you can use this type to declare functions or variables:

```tsx
const multiply: MathOperation = (a, b) => a * b;
```

### 4. **Optional and Default Parameters:**

Function types can include optional and default parameters:

```tsx
type PrintMessageFunction = (message: string, urgency?: boolean) => void;

const printMessage: PrintMessageFunction = (message, urgency = false) => {
    console.log(urgency ? `URGENT: ${message}` : message);
};
```

### 5. **Rest Parameters:**

Function types can also include rest parameters:

```tsx
type SumFunction = (...numbers: number[]) => number;

const sum: SumFunction = (...numbers) => numbers.reduce((acc, num) => acc + num, 0);
```

### 6. **Function Types as Parameters:**

You can use function types as parameters:

```tsx
type OperationFunction = (a: number, b: number) => number;

function performOperation(operation: OperationFunction, a: number, b: number): number {
    return operation(a, b);
}
```

### 7. **Generic Functions:**

You can create generic functions that work with different types:

```tsx
function identity<T>(value: T): T {
    return value;
}
```

Here, `T` is a generic type parameter.

### 8. **Function Overloads:**

You can use function overloads to specify multiple signatures for a function:

```tsx
function greet(name: string): string;
function greet(name: string, age: number): string;

function greet(name: string, age?: number): string {
    if (age !== undefined) {
        return `Hello, ${name}! You are ${age} years old.`;
    } else {
        return `Hello, ${name}!`;
    }
}
```

### 9. **Callbacks:**

Function types are commonly used with callbacks:

```tsx
type CallbackFunction = (result: number) => void;

function performOperation(a: number, b: number, callback: CallbackFunction): void {
    const result = a + b;
    callback(result);
}
```

By using function types and types for function parameters, TypeScript helps catch errors during development and provides clear interfaces for functions, contributing to code safety and readability.