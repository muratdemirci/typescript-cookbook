# Getters & Setters

## Introduction

Getters and setters are special methods that allow you to control the access and modification of class properties. Getters are used to retrieve the value of a property, while setters are used to modify the value of a property. They provide a way to encapsulate the internal representation of an object and add behavior when getting or setting its properties.

Here's an example demonstrating the use of getters and setters:

```tsx
class Circle {
  private _radius: number;

  constructor(radius: number) {
    this._radius = radius;
  }

  // Getter for the radius property
  get radius(): number {
    console.log("Getting radius");
    return this._radius;
  }

  // Setter for the radius property
  set radius(newRadius: number) {
    if (newRadius >= 0) {
      console.log("Setting radius");
      this._radius = newRadius;
    } else {
      console.error("Radius must be a non-negative value");
    }
  }

  // Getter for calculating the area
  get area(): number {
    console.log("Calculating area");
    return Math.PI * this._radius ** 2;
  }
}

// Creating an instance of the class
const myCircle = new Circle(5);

// Using the getter to retrieve the radius
console.log(myCircle.radius);  // Output: Getting radius, 5

// Using the setter to update the radius
myCircle.radius = 8;           // Output: Setting radius

// Using the getter for calculating the area
console.log(myCircle.area);    // Output: Calculating area, 201.06192982974676

// Attempting to set a negative radius (error message from the setter)
myCircle.radius = -3;          // Output: Radius must be a non-negative value
```

In this example:

- The `Circle` class has a private property `_radius` and exposes it using a getter and setter.
- The getter for `radius` allows retrieving the value of the `_radius` property with additional behavior (in this case, logging).
- The setter for `radius` allows updating the value of `_radius` with validation logic to ensure the radius is non-negative.
- A getter for `area` is included, demonstrating that getters can be used for computed properties.
- The instance of `Circle` (`myCircle`) is created and accessed using the getter and setter.

### Use Cases:

1. **Encapsulation:**
    - Getters and setters provide a way to encapsulate the internal representation of an object, allowing controlled access to properties.
2. **Validation:**
    - Setters can include validation logic to ensure that property values meet certain criteria.
3. **Computed Properties:**
    - Getters can be used to calculate and return derived or computed properties based on other properties.
4. **Logging and Side Effects:**
    - Getters and setters can be used to log property access or modification and perform additional side effects.
5. **Property Access Control:**
    - Getters and setters allow you to control read and write access to properties, enabling fine-grained access control.

By using getters and setters in TypeScript, you can design classes that provide a clean and controlled interface for accessing and modifying their properties, promoting encapsulation and maintaining the integrity of the object's state.