# "Private" and "Public" Access Modifiers

## Introduction

Access modifiers in TypeScript, such as `private` and `public`, are used to control the visibility of class members (properties and methods) within a class and its subclasses. They help enforce encapsulation and define how properties and methods can be accessed from outside the class.

### `Private` Access Modifier:

When a class member is marked as `private`, it can only be accessed within the class where it is defined. It is not accessible from outside the class, including from instances of the class or its subclasses.

```tsx
class Car {
  private speed: number;

  constructor(speed: number) {
    this.speed = speed;
  }

  accelerate(increment: number): void {
    this.speed += increment;
  }

  displaySpeed(): void {
    console.log(`Current speed: ${this.speed} km/h`);
  }
}

// Creating an instance of the class
const myCar = new Car(50);

// Accessing a private member will result in a TypeScript compilation error
// Uncommenting the line below will result in an error:
// myCar.speed = 60;

// Calling public methods is allowed
myCar.accelerate(10);
myCar.displaySpeed();  // Output: Current speed: 60 km/h
```

In this example, the `speed` property is marked as `private`, making it inaccessible from outside the `Car` class.

### `public` Access Modifier:

By default, class members are considered `public` if no access modifier is specified. `public` members are accessible from outside the class.

```tsx
class Animal {
  // By default, "legs" is public
  legs: number;

  constructor(legs: number) {
    this.legs = legs;
  }

  displayLegs(): void {
    console.log(`Number of legs: ${this.legs}`);
  }
}

// Creating an instance of the class
const dog = new Animal(4);

// Accessing public members is allowed
dog.legs = 3;           // Allowed
dog.displayLegs();      // Output: Number of legs: 3
```

In this example, the `legs` property is implicitly `public`, and it can be accessed and modified from outside the `Animal` class.

### Use Cases:

- **`private` Access Modifier:**
    - Use `private` for class members that should not be accessible from outside the class. This helps encapsulate internal details and prevents external interference.
- **`public` Access Modifier:**
    - By default, members are `public`, and this is suitable for properties and methods that need to be accessed externally.
- **Encapsulation:**
    - Access modifiers contribute to encapsulation by controlling the visibility of class members, improving code organization and maintainability.

By using `private` and `public` access modifiers appropriately, you can design classes with a clear and controlled interface, enhancing the maintainability and robustness of your TypeScript code.