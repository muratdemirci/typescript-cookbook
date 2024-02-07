# Type Aliases & Object Types

## Introduction

Type aliases can be used to create custom names for object types, making the code more readable and maintainable. Here are examples of using type aliases with object types:

## Table of Contents

- [1. **Basic Object Type Alias:**](#1-basic-object-type-alias)
- [2. **Union Object Type Alias:**](#2-union-object-type-alias)
- [3. **Object Type Alias with Functions:**](#3-object-type-alias-with-functions)
- [4. **Nested Object Type Alias:**](#4-nested-object-type-alias)
- [5. **Object Type Alias with Generics:**](#5-object-type-alias-with-generics)
- [6. **Mapped Object Type Alias:**](#6-mapped-object-type-alias)
- [7. **Combining Object Type Aliases:**](#7-combining-object-type-aliases)

### 1. **Basic Object Type Alias:**

```tsx
// Type alias for a simple object type
type Point = {
    x: number;
    y: number;
};

let origin: Point = { x: 0, y: 0 };
let position: Point = { x: 5, y: 10 };
```

### 2. **Union Object Type Alias:**

```tsx
// Type alias for a union of object types
type Shape = {
    kind: "circle";
    radius: number;
} | {
    kind: "square";
    sideLength: number;
};

let circle: Shape = { kind: "circle", radius: 5 };
let square: Shape = { kind: "square", sideLength: 4 };

```

### 3. **Object Type Alias with Functions:**

```tsx
// Type alias for an object with a function property
type MathOperations = {
    add: (a: number, b: number) => number;
    subtract: (a: number, b: number) => number;
};

let calculator: MathOperations = {
    add: (a, b) => a + b,
    subtract: (a, b) => a - b,
};
```

### 4. **Nested Object Type Alias:**

```tsx
// Nested type alias for a complex object type
type Employee = {
    id: number;
    name: string;
    contact: {
        email: string;
        phone: string;
    };
};

let employee: Employee = {
    id: 1,
    name: "John Doe",
    contact: {
        email: "john@example.com",
        phone: "123-456-7890",
    },
};
```

### 5. **Object Type Alias with Generics:**

```tsx
// Type alias for a generic object type
type Pair<T> = {
    first: T;
    second: T;
};

let numberPair: Pair<number> = { first: 1, second: 2 };
let stringPair: Pair<string> = { first: "one", second: "two" };
```

### 6. **Mapped Object Type Alias:**

```tsx
// Mapped type alias for making properties readonly
type ReadOnly<T> = {
    readonly [K in keyof T]: T[K];
};

type User = {
    id: number;
    name: string;
};

type ReadOnlyUser = ReadOnly<User>;

let user: ReadOnlyUser = { id: 1, name: "Alice" };
// user.name = "Bob"; // Error: Cannot assign to 'name' because it is a read-only property.
```

### 7. **Combining Object Type Aliases:**

```tsx
// Combining object type aliases
type Person = {
    name: string;
    age: number;
};

type Employee = Person & {
    employeeId: string;
};

let employee: Employee = { name: "John", age: 30, employeeId: "123" };
```

Using type aliases with object types allows you to create more expressive and reusable type definitions. They are especially useful when dealing with complex data structures, promoting code readability and maintainability.