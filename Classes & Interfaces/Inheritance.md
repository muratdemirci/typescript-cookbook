# Inheritance

## Introduction

Inheritance is a mechanism that allows a class (called the derived or child class) to inherit properties and methods from another class (called the base or parent class). This promotes code reuse and the creation of hierarchies of related classes. The `extends` keyword is used to establish inheritance.

```tsx
// Base class
class Animal {
  // Properties
  name: string;

  // Constructor
  constructor(name: string) {
    this.name = name;
  }

  // Method
  makeSound(): string {
    return "Some generic sound";
  }
}

// Derived class inheriting from Animal
class Dog extends Animal {
  // Additional property
  breed: string;

  // Constructor
  constructor(name: string, breed: string) {
    // Calling the constructor of the base class using super()
    super(name);
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
const myDog = new Dog("Buddy", "Golden Retriever");

// Accessing inherited properties and methods
console.log(myDog.name);      // Output: Buddy
console.log(myDog.makeSound());  // Output: Woof!
console.log(myDog.fetch());     // Output: Fetching the ball!
```

In this example:

- The `Animal` class is the base class, and the `Dog` class is the derived class.
- The `Dog` class uses the `extends` keyword to inherit from the `Animal` class.
- The `super` keyword is used in the constructor of the derived class to call the constructor of the base class and initialize inherited properties.
- The `makeSound` method is overridden in the derived class, providing a specific implementation for dogs.
- The `Dog` class introduces an additional property (`breed`) and an additional method (`fetch`).

### Access Modifiers in Inheritance:

In TypeScript, access modifiers (`public`, `protected`, and `private`) can be used to control the visibility of members within a class and its subclasses:

- `public`: Visible to everyone (default if not specified).
- `protected`: Visible to the class and its subclasses.
- `private`: Visible only within the class.

```tsx
class Animal {
  private age: number;

  constructor(age: number) {
    this.age = age;
  }

  protected getAge(): number {
    return this.age;
  }
}

class Dog extends Animal {
  // The age property is not directly accessible here

  getDogAge(): number {
    // Accessing the protected method from the base class
    return this.getAge();
  }
}

const myDog = new Dog(3);
// Error: Property 'age' is private and only accessible within class 'Animal'.
// console.log(myDog.age);

// Accessing the protected method from the derived class
console.log(myDog.getDogAge());  // Output: 3
```

### Use Cases:

- **Code Reusability:**
    - Inheritance allows the reuse of code from existing classes, reducing redundancy.
- **Polymorphism:**
    - Derived classes can provide specific implementations for methods defined in the base class, allowing polymorphic behavior.
- **Extending Functionality:**
    - Derived classes can extend the functionality of the base class by introducing new properties and methods.
- **Creating Hierarchies:**
    - Inheritance is useful for creating class hierarchies, representing relationships between different types of objects.

Inheritance is a powerful feature in TypeScript that enables the creation of more organized and reusable code by allowing classes to build upon the functionality of other classes.