# Using Types

## Introduction

The use of types is a fundamental aspect of the language, and it's one of the key features that differentiates TypeScript from JavaScript.

## Table of Contents 

- [1. **Type Annotations:**](#1-type-annotations)
- [2. **Function Parameters and Return Types:**](#2-function-parameters-and-return-types)
- [3. **Interfaces:**](#3-interfaces)
- [4. **Arrays and Generics:**](#4-arrays-and-generics)
- [5. **Union and Intersection Types:**](#5-union-and-intersection-types)
- [6. **Type Aliases:**](#6-type-aliases)
- [7. **Enums:**](#7-enums)
- [8. **Classes:**](#8-classes)
- [9. **Type Assertion:**](#9-type-assertion)
- [10. **Declaration Files (.d.ts):**](#10-declaration-files-dts)


### 1. **Type Annotations:**

- You can explicitly declare the type of a variable using type annotations. For example:
    
    ```tsx
    let name: string = "John";
    let age: number = 25;
    ```
    

### 2. **Function Parameters and Return Types:**

- Specify the types of function parameters and return values:
    
    ```tsx
    function add(x: number, y: number): number {
        return x + y;
    }
    ```
    

### 3. **Interfaces:**

- Use interfaces to define the shape of objects:
    
    ```tsx
    interface Person {
        name: string;
        age: number;
    }
    
    let person: Person = {
        name: "Alice",
        age: 30
    };
    ```
    

### 4. **Arrays and Generics:**

- Use generics to create reusable components with dynamic types:
    
    ```tsx
    let numbers: Array<number> = [1, 2, 3, 4];
    ```
    

### 5. **Union and Intersection Types:**

- Combine types using unions or intersections:
    
    ```tsx
    type Status = "success" | "error";
    type Result = { value: number } & { message: string };
    ```
    

### 6. **Type Aliases:**

- Create your own custom types with type aliases:
    
    ```tsx
    type Point = {
        x: number;
        y: number;
    };
    ```
    

### 7. **Enums:**

- Use enums to define a set of named constants:
    
    ```tsx
    enum Color {
        Red,
        Green,
        Blue
    }
    
    let myColor: Color = Color.Green;
    ```
    

### 8. **Classes:**

- Define classes with typed properties and methods:
    
    ```tsx
    class Dog {
        name: string;
    
        constructor(name: string) {
            this.name = name;
        }
    
        bark(): void {
            console.log("Woof!");
        }
    }
    
    let myDog: Dog = new Dog("Buddy");
    ```
    

### 9. **Type Assertion:**

- Use type assertion to explicitly specify a type when TypeScript cannot infer it:
    
    ```tsx
    let myVariable: any = "Hello, TypeScript!";
    let stringLength: number = (myVariable as string).length;
    ```
    

### 10. **Declaration Files (.d.ts):**

- Use declaration files to provide type information for external libraries or JavaScript code:
    
    ```tsx
    // example.d.ts
    declare module "example-library" {
        function myFunction(value: string): number;
    }
    ```

These are just a few examples of how you can use types in TypeScript. Types provide a powerful way to catch errors early in the development process, improve code documentation, and enable better tooling support in modern development environments.