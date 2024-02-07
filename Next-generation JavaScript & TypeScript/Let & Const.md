# Let & Const

The `let` and `const` keywords in JavaScript and TypeScript were introduced as part of ECMAScript 6 (ES6) and represent an enhancement to variable declarations compared to the traditional `var` keyword. Here's an overview of these next-generation variable declaration keywords:

### `let`:

- **Scope:** Variables declared with `let` have block scope, meaning they are confined to the block (enclosed by curly braces) in which they are defined. This is in contrast to `var`, which has function scope.
- **Redeclaration:** Variables declared with `let` cannot be redeclared within the same block scope. This helps avoid unintentional variable shadowing.
- **Hoisting:** Like `var`, `let` is hoisted to the top of its block scope during the compilation phase. However, unlike `var`, the variable is not initialized until the declaration statement is encountered during runtime.
- **Example:**
    
    ```tsx
    function example() {
      if (true) {
        let x = 10;
        console.log(x); // 10
      }
      console.log(x); // Error: x is not defined
    }
    ```
    

### `const`:

- **Immutable Binding:** Variables declared with `const` are constants and cannot be reassigned after initialization. The value of a `const` variable remains constant throughout its scope.
- **Block Scope:** Similar to `let`, `const` also has block scope. Once a `const` variable is assigned a value, that value cannot be changed.
- **Declaration and Initialization:** A `const` variable must be both declared and initialized at the same time. Attempting to declare a `const` variable without initialization or reassign its value later results in an error.
- **Example:**
    
    ```tsx
    function example() {
      const PI = 3.14;
      console.log(PI); // 3.14
    
      // Error: Cannot assign to 'PI' because it is a constant.
      PI = 3.14159;
    }
    ```
    

### Use Cases:

- **`let`:** Use `let` when you need a variable whose value can be reassigned, and you want to confine its scope to a specific block.
- **`const`:** Use `const` for constants or variables that should not be reassigned. This is helpful for preventing accidental mutation of values.

### TypeScript:

In TypeScript, `let` and `const` work similarly to JavaScript. TypeScript adds static typing to these variables, allowing you to explicitly specify the type or let TypeScript infer the type based on the initialization.

```tsx
let message: string = "Hello";
const PI: number = 3.14;

message = "World"; // Valid for let
// Error: Cannot assign to 'PI' because it is a constant.
PI = 3.14159; // Invalid for const
```

Using `let` and `const` in TypeScript provides the benefits of improved scoping, prevention of accidental reassignments (for `const`), and static typing for more robust code.