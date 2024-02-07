# The "unknown" Type

## Introduction

The `unknown` type represents a type-safe counterpart to the `any` type. It is used to indicate that the type of a value is unknown during development, providing a safer alternative to using `any`. Unlike `any`, variables of type `unknown` cannot be assigned to other types without explicit type checking or assertion.


## Table of Contents

- [1. **Declaration and Assignment:**](#1-declaration-and-assignment)
- [2. **Type Checking:**](#2-type-checking)
- [3. **Type Assertion:**](#3-type-assertion)
- [4. **Function Parameters with Unknown:**](#4-function-parameters-with-unknown)
- [5. **Returning "unknown" from a Function:**](#5-returning-unknown-from-a-function)
- [6. **Intersection with Known Types:**](#6-intersection-with-known-types)

### 1. **Declaration and Assignment:**

```tsx
let userInput: unknown;

userInput = 5;
userInput = 'Hello, TypeScript!';
```

In this example, `userInput` is declared with the `unknown` type, and it can be assigned values of different types.

### 2. **Type Checking:**

```tsx
let userInput: unknown = 'Hello, TypeScript!';

if (typeof userInput === 'string') {
    let strLength: number = userInput.length;
    console.log(strLength);
}
```

Type checking is required before performing operations specific to a certain type. In this case, we check if `userInput` is a string before getting its length.

### 3. **Type Assertion:**

```tsx
let userInput: unknown = 'Hello, TypeScript!';

let strLength: number = (userInput as string).length;
console.log(strLength);
```

Type assertion (`as` syntax) can be used when you are confident about the type. In this example, we assert that `userInput` is a string before getting its length.

### 4. **Function Parameters with Unknown:**

```tsx
function processInput(input: unknown): void {
    if (typeof input === 'string') {
        console.log(input.toUpperCase());
    } else {
        console.log('Input is not a string');
    }
}

processInput('Hello, TypeScript!');
processInput(42);
```

When using `unknown` in function parameters, you can perform type checking inside the function based on the actual type of the argument.

### 5. **Returning "unknown" from a Function:**

```tsx
function getUserData(): unknown {
    // ...
}

let userData: unknown = getUserData();
```

Functions can return values of type `unknown` when the specific type is not known until runtime.

### 6. **Intersection with Known Types:**

```tsx
let userInput: unknown = 'Hello, TypeScript!';

let strLength: number = (userInput as string).length; // Type assertion
let upperCaseInput: string = (userInput as string).toUpperCase(); // Type assertion
```

You can intersect `unknown` with known types using type assertions when you are confident about the type.

Using `unknown` promotes type safety by requiring explicit type checking before performing operations on values of this type. It is a more controlled alternative to using `any`, making your TypeScript code safer and more maintainable.