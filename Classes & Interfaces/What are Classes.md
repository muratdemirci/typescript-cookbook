# What are Classes?

## Introduction

Classes are a fundamental component of object-oriented programming (OOP) that provide a blueprint for creating objects with shared properties and behaviors. TypeScript adds static typing to the class-based OOP features of JavaScript.

### Basic Class Syntax:

```tsx
class Animal {
  // Properties
  name: string;
  age: number;

  // Constructor
  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }

  // Method
  makeSound(): string {
    return "Some generic sound";
  }
}

// Creating an instance of the class
const myPet = new Animal("Fluffy", 3);

// Accessing properties and calling methods
console.log(myPet.name);      // Output: Fluffy
console.log(myPet.age);       // Output: 3
console.log(myPet.makeSound());  // Output: Some generic sound
```

### Key Concepts:

1. **Class Declaration:**
    - Classes are declared using the `class` keyword followed by the class name.
2. **Properties:**
    - Class properties are variables that hold data associated with the class.
3. **Constructor:**
    - The `constructor` method is a special method that is called when an object is created from the class. It is used to initialize object properties.
4. **Methods:**
    - Class methods are functions associated with the class and can be called on instances of the class.
5. **Instance Creation:**
    - Instances of a class are created using the `new` keyword, followed by the class name and constructor arguments.
6. **Access Modifiers:**
    - TypeScript supports access modifiers (`public`, `private`, and `protected`) to control the visibility of properties and methods.

### Inheritance:

Classes in TypeScript can inherit properties and methods from other classes through inheritance. Here's an example:

```tsx
class Dog extends Animal {
  // Additional property
  breed: string;

  // Constructor
  constructor(name: string, age: number, breed: string) {
    super(name, age); // Calling the constructor of the base class
    this.breed = breed;
  }

  // Overriding the makeSound method
  makeSound(): string {
    return "Woof!";
  }

  // Additional method
  fetch(): string {
    return "Fetching the ball!";
  }
}

// Creating an instance of the derived class
const myDog = new Dog("Buddy", 2, "Golden Retriever");

// Accessing inherited properties and methods
console.log(myDog.name);      // Output: Buddy
console.log(myDog.age);       // Output: 2
console.log(myDog.makeSound());  // Output: Woof!
console.log(myDog.fetch());     // Output: Fetching the ball!
```

### TypeScript vs. JavaScript:

While classes are part of ES6 and are supported in modern JavaScript, TypeScript enhances class-based programming by providing static typing, interfaces, abstract classes, and other features that enable more robust and maintainable code.

In summary, classes in TypeScript are a way to create reusable, object-oriented code with the added benefits of static typing and other language features. They help structure code in a modular and organized manner.