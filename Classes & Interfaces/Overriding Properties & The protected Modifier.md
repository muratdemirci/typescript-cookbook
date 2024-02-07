# Overriding Properties & The "protected" Modifier

## Introduction

When you extend a class and override its methods or properties, you can use the `protected` modifier to control access to those members. The `protected` modifier allows the member to be accessed within the class and its subclasses but not from external code.

Here's an example demonstrating property overriding and the use of the `protected` modifier:

```tsx
// Base class
class Animal {
  // Protected property
  protected sound: string;

  // Constructor
  constructor(sound: string) {
    this.sound = sound;
  }

  // Method
  makeSound(): string {
    return this.sound;
  }
}

// Derived class inheriting from Animal
class Dog extends Animal {
  // Constructor with additional parameter
  constructor(sound: string, private breed: string) {
    // Calling the constructor of the base class using super()
    super(sound);
  }

  // Overriding the makeSound method
  makeSound(): string {
    // Accessing the protected property from the base class
    const baseSound = super.makeSound();

    // Adding breed information
    return `${baseSound} (Breed: ${this.breed})`;
  }
}

// Creating an instance of the derived class
const myDog = new Dog("Woof", "Golden Retriever");

// Accessing overridden method
console.log(myDog.makeSound());  // Output: Woof (Breed: Golden Retriever)

// Accessing the protected property from the base class is not allowed externally
// Error: Property 'sound' is protected and only accessible within class 'Animal' and its subclasses.
// console.log(myDog.sound);
```

In this example:

- The `Animal` class has a `protected` property `sound`. This property is accessible within the class and its subclasses but not externally.
- The `Dog` class extends `Animal` and overrides the `makeSound` method. It uses the `super` keyword to call the overridden method from the base class.
- The `Dog` class has an additional private property (`breed`), and the `makeSound` method combines the base sound with the breed information.
- The `sound` property from the base class is not directly accessible from external code.

### Use Cases:

1. **Overriding Methods:**
    - The `protected` modifier is often used when overriding methods to allow subclasses to access and modify certain aspects of the behavior.
2. **Extending Functionality:**
    - Subclasses can add additional properties or methods while building upon the functionality of the base class.
3. **Encapsulation:**
    - Using `protected` helps encapsulate the internal details of a class and provides controlled access to its members.
4. **Polymorphism:**
    - Overriding methods and properties enables polymorphic behavior, allowing different classes to be used interchangeably.

In summary, the `protected` modifier in TypeScript is useful when designing class hierarchies and allows for controlled access to properties and methods within a class and its subclasses. This promotes encapsulation and supports the principles of object-oriented programming.