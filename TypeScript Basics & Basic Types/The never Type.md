# The "never" Type

## Introduction

The `never` type represents a value that never occurs. It is used to denote functions that never return, variables that are never assigned, or expressions that always throw an exception. The `never` type is often employed in scenarios where an operation is expected to result in an unrecoverable error or when control flow should never reach a certain point.

## Table of Contents

- [1. **Functions That Never Return:**](#1-functions-that-never-return)
- [2. **Type Guards:**](#2-type-guards)
- [3. **Union Types with "never":**](#3-union-types-with-never)
- [4. **Switch Statements:**](#4-switch-statements)

### 1. **Functions That Never Return:**

```tsx
function throwError(message: string): never {
    throw new Error(message);
}

function infiniteLoop(): never {
    while (true) {
        // Infinite loop, never returns
    }
}
```

In these examples, the functions explicitly declare a return type of `never` to indicate that they never return a normal value. Instead, they throw an error or run an infinite loop.

### 2. **Type Guards:**

```tsx
function assertNever(value: never): never {
    throw new Error(`Unexpected value: ${value}`);
}

function processValue(value: string | number): void {
    if (typeof value === 'string') {
        // Process string
    } else if (typeof value === 'number') {
        // Process number
    } else {
        assertNever(value); // Unreachable code, as value cannot be any other type
    }
}
```

In this example, the `assertNever` function is used as a type guard to ensure that the function is exhaustive and handles all possible types. If control flow reaches the `assertNever` call, it means a value of an unexpected type was encountered.

### 3. **Union Types with "never":**

```tsx
type Result = number | string;

function processResult(result: Result): void {
    if (typeof result === 'number') {
        // Process number
    } else if (typeof result === 'string') {
        // Process string
    } else {
        const exhaustiveCheck: never = result; // Unreachable code
    }
}
```

The `never` type is often used in conjunction with union types to ensure that all possible types are handled.

### 4. **Switch Statements:**

```tsx
type Action = { type: 'add'; value: number } | { type: 'subtract'; value: number };

function processAction(action: Action): void {
    switch (action.type) {
        case 'add':
            // Process 'add' action
            break;
        case 'subtract':
            // Process 'subtract' action
            break;
        default:
            const exhaustiveCheck: never = action; // Unreachable code
    }
}
```

When using switch statements with discriminated unions, the `never` type can be used to ensure that all cases are handled.

Using the `never` type appropriately helps make your code more robust and ensures that unexpected scenarios are explicitly handled, improving the overall reliability of your TypeScript code.