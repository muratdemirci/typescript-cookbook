# Working with Tuples

## Introduction

Tuples are a specific type that allows you to express an array where the type of each element is known. Tuples are similar to arrays but provide a fixed-length and ordered sequence of elements.

## Table of Contents

- [1. **Basic Tuple:**](#1-basic-tuple)
- [2. **Accessing Elements:**](#2-accessing-elements)
- [3. **Updating Elements:**](#3-updating-elements)
- [4. **Tuple Destructuring:**](#4-tuple-destructuring)
- [5. **Function Returning Tuple:**](#5-function-returning-tuple)
- [6. **Optional Elements in Tuple:**](#6-optional-elements-in-tuple)
- [7. **Rest Elements in Tuple:**](#7-rest-elements-in-tuple)
- [8. **Readonly Tuple:**](#8-readonly-tuple)
- [9. **Tuple Type Assertion:**](#9-tuple-type-assertion)
- [10. **Mapped Types with Tuple:**](#10-mapped-types-with-tuple)

### 1. **Basic Tuple:**

```tsx
// Tuple with specified types
let person: [string, number, boolean] = ["John", 30, true];
```

### 2. **Accessing Elements:**

```tsx
// Accessing elements by index
let name: string = person[0]; // "John"
let age: number = person[1]; // 30
let isActive: boolean = person[2]; // true
```

### 3. **Updating Elements:**

```tsx
// Updating elements by index
person[1] = 31; // Now, age is 31
```

### 4. **Tuple Destructuring:**

```tsx
// Destructuring tuple elements
let [userName, userAge, isActiveStatus] = person;
```

### 5. **Function Returning Tuple:**

```tsx
// Function returning a tuple
function getUser(): [string, number] {
    return ["John", 30];
}

let [returnedName, returnedAge] = getUser();

```

### 6. **Optional Elements in Tuple:**

```tsx
// Tuple with optional elements
let contact: [string, string?] = ["John"];
```

### 7. **Rest Elements in Tuple:**

```tsx
// Tuple with rest elements
let team: [string, ...string[]] = ["Alice", "Bob", "Charlie"];
```

### 8. **Readonly Tuple:**

```tsx
// Readonly tuple
let readonlyTuple: readonly [string, number] = ["John", 30];
// readonlyTuple[0] = "Alice"; // Error: Index signature in type 'readonly [string, number]' only permits reading.
```

### 9. **Tuple Type Assertion:**

```tsx
// Tuple type assertion
let anyTuple: any[] = ["John", 30];
let typedTuple: [string, number] = anyTuple as [string, number];
```

### 10. **Mapped Types with Tuple:**

```tsx
// Mapped types with tuples
type ReadOnlyTuple<T> = { readonly [K in keyof T]: T[K] };

let readOnlyPerson: ReadOnlyTuple<[string, number, boolean]> = ["John", 30, true];
// readOnlyPerson[0] = "Alice"; // Error: Index signature in type 'readonly [string, number, boolean]' only permits reading.
```

Tuples are particularly useful when working with functions that return multiple values or when the order and type of elements in an array are fixed. Leverage the features provided by tuples to enhance type safety in your TypeScript code.