# "Readonly" Properties

## Introduction

The `readonly` keyword is used to make class properties or object properties immutable after their initial assignment. Once a property is marked as `readonly`, its value cannot be changed. This ensures that the property remains constant throughout the object's or class instance's lifetime.

```tsx
class Circle {
  // Readonly properties
  readonly radius: number;

  // Readonly properties can be initialized in the constructor
  constructor(radius: number) {
    this.radius = radius;
  }

  // Readonly properties cannot be reassigned
  updateRadius(newRadius: number): void {
    // Error: Cannot assign to 'radius' because it is a read-only property.
    // this.radius = newRadius;
  }

  // Readonly properties can be accessed
  calculateArea(): number {
    return Math.PI * this.radius * this.radius;
  }
}

// Creating an instance of the class
const myCircle = new Circle(5);

// Accessing readonly properties
console.log(myCircle.radius);  // Output: 5

// Readonly properties cannot be modified after initialization
// Error: Cannot assign to 'radius' because it is a read-only property.
// myCircle.radius = 10;
```

In this example:

- The `Circle` class has a `readonly` property `radius`.
- The `readonly` property is initialized in the constructor and cannot be reassigned afterward.
- An attempt to modify the `readonly` property after initialization results in a compilation error.

### Readonly Modifiers with Parameters:

You can also use `readonly` in constructor parameters to automatically create and initialize `readonly` properties:

```tsx
class Rectangle {
  // Automatically created and initialized readonly properties
  constructor(readonly width: number, readonly height: number) {}

  // Readonly properties can be accessed
  calculateArea(): number {
    return this.width * this.height;
  }
}

// Creating an instance of the class
const myRectangle = new Rectangle(4, 6);

// Accessing readonly properties
console.log(myRectangle.width);   // Output: 4
console.log(myRectangle.height);  // Output: 6

// Readonly properties cannot be modified after initialization
// Error: Cannot assign to 'width' because it is a read-only property.
// myRectangle.width = 8;
```

In this example, the `width` and `height` properties are automatically created and initialized as `readonly` based on the `readonly` modifier in the constructor parameters.

### Use Cases:

1. **Immutable Configuration:**
    - When certain properties of an object or class should remain constant throughout its lifecycle.
2. **Preventing Accidental Modifications:**
    - To avoid unintended modifications to critical properties.
3. **Documentation of Intent:**
    - Clearly indicating that a property is intended to be read-only in the code, making the code more self-explanatory.
4. **Constructor Initialization:**
    - Automatically creating and initializing read-only properties based on constructor parameters.

Using `readonly` properties in TypeScript provides a way to enforce immutability for specific properties, promoting safer and more predictable code.