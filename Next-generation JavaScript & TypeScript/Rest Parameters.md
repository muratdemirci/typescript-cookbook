# Rest Parameters

Rest parameters, introduced in ECMAScript 6 (ES6) and supported in both JavaScript and TypeScript, allow a function to accept an arbitrary number of arguments as an array. The rest parameter syntax uses the ellipsis (`...`) followed by the parameter name. Rest parameters provide a concise way to handle variable-length argument lists.

### Rest Parameters in JavaScript:

### 1. **Syntax:**

```jsx
function sum(...numbers) {
  return numbers.reduce((acc, val) => acc + val, 0);
}

console.log(sum(1, 2, 3)); // Output: 6
console.log(sum(1, 2, 3, 4, 5)); // Output: 15
```

### 2. **Rest Parameter and Regular Parameters:**

The rest parameter must be the last parameter in the function parameter list.

```jsx
function example(a, b, ...rest) {
  console.log(a); // 1
  console.log(b); // 2
  console.log(rest); // [3, 4, 5]
}

example(1, 2, 3, 4, 5);
```

### Rest Parameters in TypeScript:

### 1. **Syntax:**

In TypeScript, you can explicitly specify the type of the rest parameter as an array.

```tsx
function sum(...numbers: number[]): number {
  return numbers.reduce((acc, val) => acc + val, 0);
}
```

### 2. **Rest Parameter with Type Union:**

Rest parameters can also be combined with other parameters, and TypeScript can infer or enforce specific types.

```tsx
function printInfo(name: string, age: number, ...hobbies: string[]): void {
  console.log(`Name: ${name}, Age: ${age}`);
  console.log(`Hobbies: ${hobbies.join(', ')}`);
}
```

### Use Cases:

- **Variable-Length Argument Lists:**
Rest parameters are useful when a function needs to handle an arbitrary number of arguments.
    
    ```tsx
    function average(...numbers: number[]): number {
      const sum = numbers.reduce((acc, val) => acc + val, 0);
      return sum / numbers.length;
    }
    ```
    
- **Combining Rest Parameter with Other Parameters:**
Rest parameters can be combined with regular parameters, allowing for flexibility in function signatures.
    
    ```tsx
    function printInfo(name: string, age: number, ...hobbies: string[]): void {
      console.log(`Name: ${name}, Age: ${age}`);
      console.log(`Hobbies: ${hobbies.join(', ')}`);
    }
    ```
    
- **Array Destructuring:**
Rest parameters work well with array destructuring, allowing you to extract specific values.
    
    ```tsx
    function processArray(...elements: number[]): void {
      const [first, second, ...remaining] = elements;
      // Process individual elements or the remaining array
    }
    ```
    

Rest parameters offer a convenient way to handle functions with varying numbers of arguments, promoting flexibility and cleaner function signatures. They are particularly useful in scenarios where the exact number of arguments is not known in advance.