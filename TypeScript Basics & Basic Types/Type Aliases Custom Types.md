# Type Aliases / Custom Types

## Introduction

Type aliases (or custom types) allow you to create a named reference for a specific type or combination of types. Type aliases enhance code readability, maintainability, and can simplify complex type expressions.

## Table of Contents

- [1. **Basic Type Alias:**](#1-basic-type-alias)
- [2. **Union Type Alias:**](#2-union-type-alias)
- [3. **Object Type Alias:**](#3-object-type-alias)
- [4. **Function Type Alias:**](#4-function-type-alias)
- [5. **Generic Type Alias:**](#5-generic-type-alias)
- [6. **Combining Types with Type Alias:**](#6-combining-types-with-type-alias)
- [7. **Discriminated Union with Type Alias:**](#7-discriminated-union-with-type-alias)
- [8. **Mapped Type Alias:**](#8-mapped-type-alias)


### 1. **Basic Type Alias:**

```tsx
// Type alias for a string or number
type ID = string | number;

let userId: ID = "user123";
let orderId: ID = 456;
// let productId: ID = true; // Error: Type 'true' is not assignable to type 'ID'.
```

### 2. **Union Type Alias:**

```tsx
// Type alias for a union of string and number
type UserNameOrId = string | number;

let userName: UserNameOrId = "John";
let userId: UserNameOrId = 123;
```

### 3. **Object Type Alias:**

```tsx
// Type alias for an object with specific properties
type Point = { x: number; y: number };

let origin: Point = { x: 0, y: 0 };
let position: Point = { x: 5, y: 10 };
```

### 4. **Function Type Alias:**

```tsx
// Type alias for a function
type MathOperation = (a: number, b: number) => number;

let add: MathOperation = (a, b) => a + b;
let multiply: MathOperation = (a, b) => a * b;
```

### 5. **Generic Type Alias:**

```tsx
// Generic type alias
type Pair<T> = [T, T];

let numberPair: Pair<number> = [1, 2];
let stringPair: Pair<string> = ["hello", "world"];
```

### 6. **Combining Types with Type Alias:**

```tsx
// Combining types with type alias
type User = {
    id: number;
    username: string;
};

type AdminUser = User & { isAdmin: boolean };

let admin: AdminUser = { id: 1, username: "admin", isAdmin: true };
```

### 7. **Discriminated Union with Type Alias:**

```tsx
// Discriminated union with type alias
type Circle = { kind: "circle"; radius: number };
type Square = { kind: "square"; sideLength: number };

type Shape = Circle | Square;

function getArea(shape: Shape): number {
    switch (shape.kind) {
        case "circle":
            return Math.PI * Math.pow(shape.radius, 2);
        case "square":
            return Math.pow(shape.sideLength, 2);
    }
}
```

### 8. **Mapped Type Alias:**

```tsx
// Mapped type alias
type ReadOnly<T> = {
    readonly [K in keyof T]: T[K];
};

type User = {
    id: number;
    name: string;
};

type ReadOnlyUser = ReadOnly<User>;
```

Type aliases are especially useful when you need to reuse complex type definitions across your codebase or create more expressive names for types. They provide a way to create custom abstractions and improve the maintainability of your TypeScript code.