# Literal Types

## Introduction

Literal types allow you to specify exact values that a variable can have. Literal types are specific values, such as strings, numbers, or booleans, and they are denoted by the actual value itself. This allows for more precise type definitions in certain scenarios.

## Table of Contents

- [1. **String Literal Types:**](#1-string-literal-types)
- [2. **Numeric Literal Types:**](#2-numeric-literal-types)
- [3. **Boolean Literal Types:**](#3-boolean-literal-types)
- [4. **Literal Types in Function Parameters:**](#4-literal-types-in-function-parameters)
- [5. **Literal Types with Type Aliases:**](#5-literal-types-with-type-aliases)
- [6. **Combining Literal Types:**](#6-combining-literal-types)
- [7. **Discriminated Unions:**](#7-discriminated-unions)

### 1. **String Literal Types:**

```tsx
// Variable with a string literal type
let color: "red" | "green" | "blue";
color = "red";    // OK
color = "green";  // OK
// color = "yellow"; // Error: Type '"yellow"' is not assignable to type '"red" | "green" | "blue"'.
```

### 2. **Numeric Literal Types:**

```tsx
// Variable with a numeric literal type
let statusCode: 200 | 404 | 500;
statusCode = 200;    // OK
// statusCode = 300; // Error: Type '300' is not assignable to type '200 | 404 | 500'.
```

### 3. **Boolean Literal Types:**

```tsx
// Variable with a boolean literal type
let isTrue: true;
isTrue = true;    // OK
// isTrue = false; // Error: Type 'false' is not assignable to type 'true'.
```

### 4. **Literal Types in Function Parameters:**

```tsx
// Function with string literal type parameter
function setColor(newColor: "red" | "green" | "blue"): void {
    // Implementation...
}

setColor("red");    // OK
// setColor("yellow"); // Error: Argument of type '"yellow"' is not assignable to parameter of type '"red" | "green" | "blue"'.
```

### 5. **Literal Types with Type Aliases:**

```tsx
// Type alias with string literal types
type Direction = "up" | "down" | "left" | "right";

let direction: Direction = "up";    // OK
// direction = "diagonal";          // Error: Type '"diagonal"' is not assignable to type 'Direction'.
```

### 6. **Combining Literal Types:**

```tsx
// Union of string and numeric literal types
let literalUnion: "one" | "two" | 1 | 2;
literalUnion = "two"; // OK
literalUnion = 1;     // OK
// literalUnion = 3;    // Error: Type '3' is not assignable to type '"one" | "two" | 1 | 2'.
```

### 7. **Discriminated Unions:**

Literal types are often used in discriminated unions to create exhaustive checks.

```tsx
interface Circle {
    kind: "circle";
    radius: number;
}

interface Square {
    kind: "square";
    sideLength: number;
}

type Shape = Circle | Square;

function getArea(shape: Shape): number {
    switch (shape.kind) {
        case "circle":
            return Math.PI * Math.pow(shape.radius, 2);
        case "square":
            return Math.pow(shape.sideLength, 2);
        default:
            return 0;
    }
}
```

Literal types provide a way to express specific values as types, and they are particularly useful when you want to narrow down the possible values a variable can have. They contribute to TypeScript's static type checking by making the types more precise and preventing unintended values.