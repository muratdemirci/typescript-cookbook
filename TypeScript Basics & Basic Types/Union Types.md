# Union Types

## Introduction

Union types allow you to express a value that can have one of several types. This provides flexibility when a variable or parameter can accept multiple types. Union types are denoted by the `|` (pipe) symbol.

## Table of Contents

- [1. **Basic Union Type:**](#1-basic-union-type)
- [2. **Union Type in Function Parameters:**](#2-union-type-in-function-parameters)
- [3. **Union Types with Arrays:**](#3-union-types-with-arrays)
- [4. **Union Types in Object Properties:**](#4-union-types-in-object-properties)
- [5. **Union Types with Type Guard:**](#5-union-types-with-type-guard)
- [6. **Union Types with Enums:**](#6-union-types-with-enums)
- [7. **Union Types in Type Aliases:**](#7-union-types-in-type-aliases)

### 1. **Basic Union Type:**

```tsx
// A variable that can be either a number or a string
let ageOrName: number | string;
ageOrName = 25;       // OK
ageOrName = "John";   // OK
// ageOrName = true;   // Error: Type 'boolean' is not assignable to type 'number | string'.
```

### 2. **Union Type in Function Parameters:**

```tsx
// Function parameter that can be either a number or a string
function displayData(data: number | string): void {
    console.log(data);
}

displayData(42);      // OK
displayData("Hello"); // OK
// displayData(true); // Error: Type 'boolean' is not assignable to type 'number | string'.
```

### 3. **Union Types with Arrays:**

```tsx
// Array that can contain either numbers or strings
let numericOrStringArray: (number | string)[] = [1, "two", 3, "four"];
```

### 4. **Union Types in Object Properties:**

```tsx
// Object with properties of different types
interface Person {
    name: string;
    age: number | string;
}

let john: Person = { name: "John", age: 25 };
let alice: Person = { name: "Alice", age: "unknown" };
```

### 5. **Union Types with Type Guard:**

```tsx
// Using typeof to perform type guard
function printData(data: number | string): void {
    if (typeof data === "number") {
        console.log("It's a number:", data);
    } else {
        console.log("It's a string:", data);
    }
}

printData(42);      // It's a number: 42
printData("Hello"); // It's a string: Hello
```

### 6. **Union Types with Enums:**

```tsx
// Union type with enums
enum Shape {
    Circle,
    Square,
}

function getArea(shape: Shape | null): number {
    switch (shape) {
        case Shape.Circle:
            return Math.PI * Math.pow(2, 2);
        case Shape.Square:
            return Math.pow(4, 2);
        default:
            return 0;
    }
}

console.log(getArea(Shape.Circle)); // Output: 12.566370614359172
```

### 7. **Union Types in Type Aliases:**

```tsx
// Type alias with union type
type Result = string | number;

let result1: Result = "Success";
let result2: Result = 42;
```

Union types provide a way to express more flexible and dynamic type scenarios in TypeScript. It's important to use them judiciously and consider type guards or other techniques when working with variables that have union types to maintain type safety.