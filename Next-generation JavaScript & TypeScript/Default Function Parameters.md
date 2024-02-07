# Default Function Parameters

Default function parameters, introduced in ECMAScript 6 (ES6) and supported in both JavaScript and TypeScript, allow you to specify default values for function parameters. This feature provides a more concise way to handle optional parameters and ensures that a function can still be called successfully even if some parameters are not provided.

### Default Function Parameters in JavaScript:

1. **Syntax:**
    
    ```jsx
    // ES6 Default Parameter Syntax
    function greet(name = "Guest", greeting = "Hello") {
      console.log(`${greeting}, ${name}!`);
    }
    
    // Calling the function without providing parameters
    greet(); // Output: Hello, Guest!
    
    // Calling the function with provided parameters
    greet("John", "Hi"); // Output: Hi, John!
    ```
    
2. **Positional Defaults:**
Default parameters are positional, meaning that if a default value is specified for a parameter, all subsequent parameters must also have default values.
    
    ```jsx
    // Valid: Defaults are provided for both parameters
    function example(a = 1, b = 2) {
      // Function body
    }
    
    // Invalid: If a default is provided for 'b', a default must be provided for 'a' as well
    function invalidExample(a, b = 2) {
      // Function body
    }
    ```
    

### Default Function Parameters in TypeScript:

1. **Syntax:**
In TypeScript, default parameters work similarly to JavaScript. You can specify default values and optionally include type annotations.
    
    ```tsx
    // TypeScript Default Parameter Syntax
    function greet(name: string = "Guest", greeting: string = "Hello"): void {
      console.log(`${greeting}, ${name}!`);
    }
    ```
    
2. **Type Annotations:**
TypeScript allows you to include type annotations for default parameters to enforce the expected types.
    
    ```tsx
    // TypeScript Default Parameter with Type Annotations
    function add(a: number, b: number = 0): number {
      return a + b;
    }
    ```
    
3. **Rest Parameters and Default Values:**
You can use rest parameters (`...rest`) along with default values to handle an arbitrary number of additional parameters.
    
    ```tsx
    // TypeScript Rest Parameter with Default Values
    function concatenate(separator: string = ", ", ...strings: string[]): string {
      return strings.join(separator);
    }
    ```
    

### Use Cases:

- **Handling Optional Parameters:**
Default parameters are useful for making function parameters optional without explicitly checking for `undefined` or using conditional logic.
    
    ```tsx
    function printDetails(name: string, age?: number, city: string = "Unknown"): void {
      console.log(`Name: ${name}, Age: ${age || "Not specified"}, City: ${city}`);
    }
    ```
    
- **Providing Default Values:**
When a parameter is not provided, the default value ensures that the function still behaves as expected.
    
    ```tsx
    function greet(name: string = "Guest", greeting: string = "Hello"): void {
      console.log(`${greeting}, ${name}!`);
    }
    ```
    
- **Avoiding `undefined`:**
Default parameters can help avoid issues related to `undefined` values when a parameter is not provided.
    
    ```tsx
    function processData(data: string[] = []): void {
      // Process the data array
    }
    ```
    

Default function parameters provide a convenient way to make functions more flexible, handle optional parameters, and set default values, improving the readability and maintainability of code.