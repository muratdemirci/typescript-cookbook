# Function Return Types & "void”

## Introduction

Function return types specify the type of the value that a function will return. The `void` type is used when a function does not return any value.

## Table of Contents

- [1. **Specifying Function Return Types:**](#1-specifying-function-return-types)
- [2. **Void Return Type:**](#2-void-return-type)
- [3. **Functions with No Return Type:**](#3-functions-with-no-return-type)
- [4. **Using "undefined" Return Type:**](#4-using-undefined-return-type)
- [5. **Never Return Type:**](#5-never-return-type)
- [6. **Function Type Declarations:**](#6-function-type-declarations)

### 1. **Specifying Function Return Types:**

You can explicitly specify the return type of a function using the `: returnType` syntax.

```tsx
function add(a: number, b: number): number {
    return a + b;
}
```

In this example, the function `add` takes two parameters of type `number` and returns a value of type `number`.

### 2. **Void Return Type:**

The `void` type is used when a function does not return any value. It indicates that the function performs an action but does not produce a result.

```tsx
function logMessage(message: string): void {
    console.log(message);
}
```

Here, `logMessage` logs a message to the console but does not return a value.

### 3. **Functions with No Return Type:**

When a function does not have a `return` statement or the `return` statement has no expression, TypeScript infers the return type as `void`.

```tsx
function greet(name: string): void {
    console.log(`Hello, ${name}!`);
}

function throwError(message: string): never {
    throw new Error(message);
}
```

In the `greet` function, TypeScript infers `void` because there is no explicit return type and no `return` statement with an expression.

### 4. **Using "undefined" Return Type:**

You can also use the `undefined` type as a return type to indicate that the function returns a value of `undefined`.

```tsx
function getOption(option: string): string | undefined {
    if (option === "enabled") {
        return "The option is enabled.";
    } else {
        return undefined;
    }
}
```

In this example, the function `getOption` returns either a string or `undefined`.

### 5. **Never Return Type:**

The `never` type is used when a function never produces a value or always throws an exception.

```tsx
function throwError(message: string): never {
    throw new Error(message);
}
```

Here, the `throwError` function has a `never` return type because it always throws an exception.

### 6. **Function Type Declarations:**

When using function type declarations, you can also specify the return type.

```tsx
type MathOperation = (a: number, b: number) => number;

const add: MathOperation = (a, b) => a + b;
const subtract: MathOperation = (a, b) => a - b;
```

In this example, the `MathOperation` type defines functions that take two parameters of type `number` and return a value of type `number`.

Understanding function return types and using them appropriately enhances the clarity and maintainability of your TypeScript code, as it helps TypeScript catch potential errors during development.