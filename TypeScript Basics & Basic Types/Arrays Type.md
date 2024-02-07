# Arrays Types

## Introduction

You can define types for arrays to specify the types of elements they contain. Here are several ways to work with array types:

## Table of Contents

- [1. **Basic Array Types:**](#1-basic-array-types)
- [2. **Array Type with Union:**](#2-array-type-with-union)
- [3. **Array Type with Generics:**](#3-array-type-with-generics)
- [4. **Tuple Types:**](#4-tuple-types)
- [5. **Array of Objects:**](#5-array-of-objects)
- [6. **Readonly Arrays:**](#6-readonly-arrays)
- [7. **Array Type Assertion:**](#7-array-type-assertion)
- [8. **Array Type Inference:**](#8-array-type-inference)
- [9. **Rest Parameters and Spread Operator:**](#9-rest-parameters-and-spread-operator)
- [10. **Array Methods with Type Inference:**](#10-array-methods-with-type-inference)

### 1. **Basic Array Types:**

```tsx
// Array of numbers
let numbers: number[] = [1, 2, 3, 4, 5];

// Array of strings
let names: string[] = ["John", "Alice", "Bob"];

// Array of booleans
let flags: boolean[] = [true, false, true];
```

### 2. **Array Type with Union:**

```tsx
// Array of numbers or strings
let mixedArray: (number | string)[] = [1, "two", 3, "four"];
```

### 3. **Array Type with Generics:**

```tsx
// Generic array type
let genericArray: Array<number> = [1, 2, 3];
```

### 4. **Tuple Types:**

Tuples allow you to specify the type of each element at a specific position in the array.

```tsx
// Tuple with specified types
let tuple: [string, number, boolean] = ["John", 30, true];
```

### 5. **Array of Objects:**

```tsx
// Array of objects with a specific shape
type Person = { name: string; age: number };
let people: Person[] = [
    { name: "John", age: 30 },
    { name: "Alice", age: 25 },
];
```

### 6. **Readonly Arrays:**

```tsx
// Readonly array
let readonlyArray: ReadonlyArray<number> = [1, 2, 3];
// readonlyArray[0] = 4; // Error: Index signature in type 'readonly number[]' only permits reading.
```

### 7. **Array Type Assertion:**

```tsx
// Array type assertion
let anyArray: any[] = [1, "two", true];
let stringArray: string[] = anyArray as string[];
```

### 8. **Array Type Inference:**

```tsx
// TypeScript infers the array type
let inferredArray = [1, 2, 3]; // inferredArray is of type number[]
```

### 9. **Rest Parameters and Spread Operator:**

```tsx
// Rest parameters in function
function mergeArrays(...arrays: number[][]): number[] {
    return [].concat(...arrays);
}

let merged: number[] = mergeArrays([1, 2], [3, 4], [5, 6]);
```

### 10. **Array Methods with Type Inference:**

```tsx
// Array methods with type inference
let numbers = [1, 2, 3];
let doubledNumbers = numbers.map((num) => num * 2); // doubledNumbers is inferred as number[]
```

These examples illustrate different ways to define and use array types in TypeScript. Choose the approach that best fits your use case, and leverage TypeScript's static typing to catch potential errors early in the development process.