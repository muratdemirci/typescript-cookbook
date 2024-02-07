# Type Casing

## Introduction

Type names and type aliases conventionally use PascalCase. PascalCase is a naming convention where the first letter of each word is capitalized, and there are no underscores between words. This convention helps distinguish types from variables and makes the code more readable. Here are some examples:

## Table of Contents

- [1. **Interfaces:**](#1-interfaces)
- [2. **Type Aliases:**](#2-type-aliases)
- [3. **Enums:**](#3-enums)
- [4. **Classes:**](#4-classes)
- [5. **Type Parameters (Generics):**](#5-type-parameters-generics)
- [6. **Declaration Files (.d.ts):**](#6-declaration-files-dts)

### 1. **Interfaces:**

- **PascalCase:**
    
    ```tsx
    interface Point {
        x: number;
        y: number;
    }
    ```
    

### 2. **Type Aliases:**

- **PascalCase:**
    
    ```tsx
    type EmployeeInfo = {
        name: string;
        age: number;
    };
    ```
    

### 3. **Enums:**

- **PascalCase:**
    
    ```tsx
    enum Color {
        Red,
        Green,
        Blue
    }
    ```
    

### 4. **Classes:**

- **PascalCase for Class Names:**
    
    ```tsx
    class Car {
        // class members here
    }
    ```
    

### 5. **Type Parameters (Generics):**

- **Single Letter in PascalCase:**
    
    ```tsx
    function identity<T>(value: T): T {
        return value;
    }
    ```
    

### 6. **Declaration Files (.d.ts):**

- **PascalCase for Module and Type Names:**
    
    ```tsx
    // example.d.ts
    declare module "ExampleLibrary" {
        function myFunction(value: string): number;
    }
    ```
    

This consistent naming convention enhances code readability and maintains a clear distinction between types and variables or functions in your TypeScript code. It's important to follow these conventions for consistency and to make your code more accessible to other developers who might work on the project.