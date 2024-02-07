# Functions as Types

## Introduction

Functions can be treated as types, allowing you to define and use function types in a similar way to other types. This concept is known as "Functions as Types" or "Function Types." Here's how you can work with function types in TypeScript:

## Table of Contents

- [1. **Function Type Declarations:**](#1-function-type-declarations)
- [2. **Function Interfaces:**](#2-function-interfaces)
- [3. **Type Aliases for Functions:**](#3-type-aliases-for-functions)
- [4. **Optional and Default Parameters:**](#4-optional-and-default-parameters)
- [5. **Rest Parameters:**](#5-rest-parameters)
- [6. **Function Types in Generics:**](#6-function-types-in-generics)

### 1. **Function Type Declarations:**

You can declare a function type using the `type` keyword or `interface` keyword.

```tsx
type MathOperation = (a: number, b: number) => number;

const add: MathOperation = (a, b) => a + b;
const subtract: MathOperation = (a, b) => a - b;
```

In this example, the `MathOperation` type represents a function that takes two parameters of type `number` and returns a value of type `number`. The `add` and `subtract` functions are assigned to this type.

### 2. **Function Interfaces:**

You can use the `interface` keyword to define function types as well.

```tsx
interface MathOperation {
    (a: number, b: number): number;
}

const multiply: MathOperation = (a, b) => a * b;
const divide: MathOperation = (a, b) => a / b;
```

The `MathOperation` interface is essentially a function type, and the `multiply` and `divide` functions conform to this interface.

### 3. **Type Aliases for Functions:**

You can also use type aliases for function types.

```tsx
type GreetingFunction = (name: string) => void;

const greet: GreetingFunction = (name) => console.log(`Hello, ${name}!`);
```

Here, `GreetingFunction` is a type alias for a function that takes a `string` parameter and returns `void`.

### 4. **Optional and Default Parameters:**

Function types can also include optional and default parameters.

```tsx
type PrintMessageFunction = (message: string, urgency?: boolean) => void;

const printMessage: PrintMessageFunction = (message, urgency = false) => {
    console.log(urgency ? `URGENT: ${message}` : message);
};
```

### 5. **Rest Parameters:**

Function types can include rest parameters.

```tsx
type SumFunction = (...numbers: number[]) => number;

const sum: SumFunction = (...numbers) => numbers.reduce((acc, num) => acc + num, 0);
```

Here, `SumFunction` represents a function that takes any number of parameters and returns a number.

### 6. **Function Types in Generics:**

Function types can be used in generics to create flexible and reusable components.

```tsx
type TransformFunction<T> = (input: T) => T;

function applyTransformation<T>(value: T, transform: TransformFunction<T>): T {
    return transform(value);
}

const addOne: TransformFunction<number> = (num) => num + 1;
const capitalize: TransformFunction<string> = (str) => str.toUpperCase();

const result1 = applyTransformation(5, addOne); // Result: 6
const result2 = applyTransformation("hello", capitalize); // Result: "HELLO"
```

In this example, `TransformFunction` is a generic function type that can be applied to different types.

Using functions as types allows you to define clear and reusable interfaces for your functions, promoting code readability and maintainability in TypeScript.