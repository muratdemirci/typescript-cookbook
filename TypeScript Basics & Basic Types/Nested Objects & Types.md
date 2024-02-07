# Nested Objects & Types

## Introduction

You can define types for nested objects to represent complex data structures. Let's explore how to define nested objects and types for them:

## Table of Contents

- [1. **Simple Nested Object:**](#1-simple-nested-object)
- [2. **Optional Properties in Nested Objects:**](#2-optional-properties-in-nested-objects)
- [3. **Nested Arrays:**](#3-nested-arrays)
- [4. **Recursive Types:**](#4-recursive-types)
- [5. **Union Types for Nested Objects:**](#5-union-types-for-nested-objects)
- [6. **Mapped Types for Nested Objects:**](#6-mapped-types-for-nested-objects)

### 1. **Simple Nested Object:**

```tsx
type Address = {
    street: string;
    city: string;
    zipCode: string;
};

type Person = {
    name: string;
    age: number;
    address: Address;
};

const john: Person = {
    name: "John",
    age: 30,
    address: {
        street: "123 Main St",
        city: "Anytown",
        zipCode: "12345",
    },
};
```

### 2. **Optional Properties in Nested Objects:**

```tsx
type OptionalAddress = {
    street?: string;
    city?: string;
    zipCode?: string;
};

type OptionalPerson = {
    name: string;
    age: number;
    address?: OptionalAddress;
};

const alice: OptionalPerson = {
    name: "Alice",
    age: 25,
    // address is optional
};

```

### 3. **Nested Arrays:**

```tsx
type OrderItem = {
    productName: string;
    quantity: number;
};

type Order = {
    orderId: string;
    items: OrderItem[];
};

const myOrder: Order = {
    orderId: "123456",
    items: [
        { productName: "Laptop", quantity: 2 },
        { productName: "Mouse", quantity: 1 },
    ],
};
```

### 4. **Recursive Types:**

You can create recursive types for nested structures that reference themselves.

```tsx
type TreeNode<T> = {
    value: T;
    children?: TreeNode<T>[];
};

const tree: TreeNode<number> = {
    value: 1,
    children: [
        {
            value: 2,
            children: [
                { value: 4 },
                { value: 5 },
            ],
        },
        {
            value: 3,
            children: [
                { value: 6 },
                { value: 7 },
            ],
        },
    ],
};
```

### 5. **Union Types for Nested Objects:**

```tsx
type Circle = { kind: "circle"; radius: number };
type Square = { kind: "square"; sideLength: number };
type Shape = Circle | Square;

const circle: Shape = { kind: "circle", radius: 5 };
const square: Shape = { kind: "square", sideLength: 4 };
```

### 6. **Mapped Types for Nested Objects:**

```tsx
type Flatten<T> = {
    [K in keyof T]: T[K] extends object ? Flatten<T[K]> : T[K];
};

type NestedObject = {
    prop1: {
        prop2: {
            prop3: number;
        };
        prop4: string;
    };
    prop5: boolean;
};

type FlatObject = Flatten<NestedObject>;
// Result: { prop1_prop2_prop3: number; prop1_prop4: string; prop5: boolean; }
```

These examples showcase different ways to represent and work with nested objects and types in TypeScript. Choose the approach that best fits the structure and requirements of your data. Using types effectively ensures type safety and helps catch potential errors during development.