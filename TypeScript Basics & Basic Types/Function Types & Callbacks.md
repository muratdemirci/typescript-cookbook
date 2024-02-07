# Function Types & Callbacks

## Introduction

Function types and callbacks are integral concepts that enhance the flexibility and type safety of your code. Let's explore how function types and callbacks work in TypeScript.

## Table of Contents

- [1. **Function Types:**](#1-function-types)
- [2. **Callbacks:**](#2-callbacks)
- [3. **Function Types with Callbacks:**](#3-function-types-with-callbacks)

### 1. **Function Types:**

Function types define the shape of a function, including the types of its parameters and the type of its return value. Here's an example:

```tsx
type MathOperation = (a: number, b: number) => number;

const add: MathOperation = (a, b) => a + b;
const subtract: MathOperation = (a, b) => a - b;
```

In this example, `MathOperation` is a function type representing a function that takes two `number` parameters and returns a `number`. The `add` and `subtract` functions conform to this type.

### 2. **Callbacks:**

Callbacks are functions passed as arguments to other functions. They are commonly used in asynchronous operations and event handling. Here's an example of a callback in TypeScript:

```tsx
type CallbackFunction = (result: number) => void;

function performOperation(a: number, b: number, callback: CallbackFunction): void {
    const result = a + b;
    callback(result);
}

// Using the performOperation function with a callback
const printResult: CallbackFunction = (result) => {
    console.log(`Result: ${result}`);
};

performOperation(3, 7, printResult);
```

In this example, `CallbackFunction` is a type representing a callback function that takes a `number` parameter and returns `void`. The `performOperation` function takes two numbers and a callback function, performs an operation, and invokes the callback with the result.

### 3. **Function Types with Callbacks:**

You can combine function types and callbacks to define clear interfaces for functions that accept callbacks. Here's an example:

```tsx
type OperationCallback = (result: number) => void;
type MathOperationWithCallback = (a: number, b: number, callback: OperationCallback) => void;

const addWithCallback: MathOperationWithCallback = (a, b, callback) => {
    const result = a + b;
    callback(result);
};

// Using the addWithCallback function
addWithCallback(5, 8, (result) => {
    console.log(`Sum: ${result}`);
});
```

In this example, `OperationCallback` is a type representing a callback function, and `MathOperationWithCallback` is a function type representing a math operation that accepts two numbers and a callback. The `addWithCallback` function conforms to this type.

By utilizing function types and callbacks, TypeScript allows you to express clear and reusable patterns in your code, improving type safety and enhancing the readability of your functions.