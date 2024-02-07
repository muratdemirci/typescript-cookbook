# TypeScript Types vs JavaScript Types

## Introduction

TypeScript and JavaScript share some common types as both languages are designed to be compatible. However, TypeScript introduces additional features and concepts related to types that go beyond what is available in JavaScript. Here's a comparison between TypeScript types and JavaScript types:

## Table of Contents 

- [Common Types in TypeScript and JavaScript:](#common-types-in-typescript-and-javascript)
- [Additional TypeScript Types and Features:](#additional-typescript-types-and-features)

### Common Types in TypeScript and JavaScript:

1. **Primitive Types:**
    - **JavaScript:**
        
        ```jsx
        let num = 5; // Number
        let str = "Hello"; // String
        let bool = true; // Boolean
        ```
        
    - **TypeScript:**
        
        ```tsx
        let num: number = 5;
        let str: string = "Hello";
        let bool: boolean = true;
        ```
        
2. **Object:**
    - **JavaScript:**
        
        ```jsx
        let obj = { key: "value" };
        ```
        
    - **TypeScript:**
        
        ```tsx
        let obj: { key: string } = { key: "value" };
        ```
        
3. **Arrays:**
    - **JavaScript:**
        
        ```jsx
        let arr = [1, 2, 3];
        ```
        
    - **TypeScript:**
        
        ```tsx
        let arr: number[] = [1, 2, 3];
        ```
        

### Additional TypeScript Types and Features:

1. **Union Types:**
    - **TypeScript:**
        
        ```tsx
        let value: number | string;
        value = 10; // Valid
        value = "Hello"; // Valid
        ```
        
2. **Type Aliases:**
    - **TypeScript:**
        
        ```tsx
        type Point = { x: number; y: number };
        let p: Point = { x: 1, y: 2 };
        ```
        
3. **Interfaces:**
    - **TypeScript:**
        
        ```tsx
        interface Person {
            name: string;
            age: number;
        }
        let person: Person = { name: "John", age: 30 };
        ```
        
4. **Enums:**
    - **TypeScript:**
        
        ```tsx
        enum Color {
            Red,
            Green,
            Blue
        }
        let myColor: Color = Color.Green;
        ```
        
5. **Function Types:**
    - **TypeScript:**
        
        ```tsx
        type AddFunction = (a: number, b: number) => number;
        let add: AddFunction = (a, b) => a + b;
        ```
        
6. **Generics:**
    - **TypeScript:**
        
        ```tsx
        function identity<T>(arg: T): T {
            return arg;
        }
        let result: number = identity(10);
        ```
        
7. **Nullable Types:**
    - **TypeScript:**
        
        ```tsx
        let value: number | null = null;
        ```
        
8. **Type Assertion:**
    - **TypeScript:**
        
        ```tsx
        let variable: any = "Hello, TypeScript!";
        let length: number = (variable as string).length;
        ```
        
9. **Declaration Files (.d.ts):**
    - **TypeScript:**
        
        ```tsx
        // example.d.ts
        declare module "example-library" {
            function myFunction(value: string): number;
        }
        ```
        

These additional TypeScript features provide more expressive power, enhance code readability, and catch errors during development, leading to more maintainable and robust codebases compared to JavaScript alone.