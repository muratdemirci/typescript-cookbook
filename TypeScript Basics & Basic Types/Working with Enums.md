# Working with Enums

## Introduction

Enums (enumerations) in TypeScript allow you to define a set of named constant values representing discrete elements or categories. Enumerations make your code more readable and maintainable by providing meaningful names for specific values. 

## Table of Contents 

- [1. **Numeric Enums:**](#1-numeric-enums)
- [2. **String Enums:**](#2-string-enums)
- [3. **Accessing Enum Values:**](#3-accessing-enum-values)
- [4. **Enums with Explicit Values:**](#4-enums-with-explicit-values)
- [5. **Reverse Mapping:**](#5-reverse-mapping)
- [6. **Heterogeneous Enums:**](#6-heterogeneous-enums)
- [7. **Const Enums:**](#7-const-enums)
- [8. **Enums in Functions:**](#8-enums-in-functions)

### 1. **Numeric Enums:**

Numeric enums assign numeric values to each member, starting from 0 by default.

```tsx
enum Direction {
    Up,       // 0
    Down,     // 1
    Left,     // 2
    Right,    // 3
}

let myDirection: Direction = Direction.Up;
console.log(myDirection); // Output: 0
```

### 2. **String Enums:**

String enums allow you to use strings instead of numbers for enum values.

```tsx
enum Color {
    Red = "RED",
    Green = "GREEN",
    Blue = "BLUE",
}

let myColor: Color = Color.Green;
console.log(myColor); // Output: "GREEN"
```

### 3. **Accessing Enum Values:**

You can access enum values by their names or numeric values.

```tsx
console.log(Direction.Up);     // Output: 0
console.log(Direction[2]);      // Output: "Left"
console.log(Color.Red);         // Output: "RED"
```

### 4. **Enums with Explicit Values:**

You can assign explicit values to enum members.

```tsx
enum StatusCode {
    OK = 200,
    NotFound = 404,
    InternalServerError = 500,
}

let status: StatusCode = StatusCode.OK;
console.log(status); // Output: 200
```

### 5. **Reverse Mapping:**

Enums support reverse mapping, allowing you to get the name of an enum member from its value.

```tsx
console.log(Direction[0]);         // Output: "Up"
console.log(Color["GREEN"]);       // Output: "Green"
console.log(StatusCode[404]);      // Output: "NotFound"
```

### 6. **Heterogeneous Enums:**

You can mix numeric and string values in a single enum.

```tsx
enum MixedEnum {
    A = 1,
    B = "B",
    C = 3,
}

let mixedValue: MixedEnum = MixedEnum.B;
console.log(mixedValue); // Output: "B"
```

### 7. **Const Enums:**

Using the `const` modifier makes TypeScript replace enum references with their literal values during compilation.

```tsx
const enum Size {
    Small,
    Medium,
    Large,
}

let itemSize: Size = Size.Medium;
// During compilation, the above line is transformed to:
// let itemSize = 1;
```

### 8. **Enums in Functions:**

Enums are commonly used to improve readability in functions.

```tsx
enum TrafficLight {
    Red,
    Yellow,
    Green,
}

function getTrafficLightColor(color: TrafficLight): string {
    switch (color) {
        case TrafficLight.Red:
            return "Stop";
        case TrafficLight.Yellow:
            return "Proceed with caution";
        case TrafficLight.Green:
            return "Go";
        default:
            return "Unknown";
    }
}

let currentColor: TrafficLight = TrafficLight.Green;
console.log(getTrafficLightColor(currentColor)); // Output: "Go"
```

Enums provide a way to define a set of named values and enhance code readability by using meaningful names instead of raw numbers or strings. Choose the appropriate type of enum (numeric, string, etc.) based on your specific use case.