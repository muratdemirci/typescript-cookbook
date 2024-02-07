# Array & Object Destructuring

Array and object destructuring are features introduced in ECMAScript 6 (ES6) and are supported in both JavaScript and TypeScript. They provide a concise syntax for extracting values from arrays and objects, making code more readable and enabling a more expressive programming style.

### Array Destructuring:

### 1. **Basic Syntax:**

```jsx
const numbers = [1, 2, 3, 4, 5];
const [first, second, third] = numbers;

console.log(first); // Output: 1
console.log(second); // Output: 2
console.log(third); // Output: 3
```

### 2. **Skipping Elements:**

You can skip elements by leaving empty spaces in the destructuring pattern.

```jsx
const [first, , third] = numbers;
```

### 3. **Rest Parameter:**

Use the rest parameter (`...`) to capture remaining elements into an array.

```jsx
const [first, ...rest] = numbers;
```

### Object Destructuring:

### 1. **Basic Syntax:**

```jsx
const person = { name: 'John', age: 30, city: 'New York' };
const { name, age, city } = person;

console.log(name); // Output: John
console.log(age); // Output: 30
console.log(city); // Output: New York
```

### 2. **Renaming Variables:**

You can rename variables during destructuring.

```jsx
const { name: fullName, age: userAge } = person;
```

### 3. **Default Values:**

Provide default values for variables in case the property is undefined.

```jsx
const { name, age, city = 'Unknown' } = person;
```

### Destructuring in TypeScript:

### 1. **Array Destructuring in TypeScript:**

```tsx
const numbers: number[] = [1, 2, 3, 4, 5];
const [first, second, third]: number[] = numbers;
```

### 2. **Object Destructuring in TypeScript:**

```tsx
interface Person {
  name: string;
  age: number;
  city: string;
}

const person: Person = { name: 'John', age: 30, city: 'New York' };
const { name, age, city }: Person = person;
```

### 3. **Function Parameter Destructuring in TypeScript:**

Destructuring in function parameters is commonly used in TypeScript.

```tsx
function printPersonInfo({ name, age, city }: Person): void {
  console.log(`Name: ${name}, Age: ${age}, City: ${city}`);
}
```

### Use Cases:

- **Simplified Variable Assignment:**
Destructuring allows you to assign values to variables more conveniently, especially when dealing with arrays or objects.
    
    ```tsx
    const numbers: number[] = [1, 2, 3];
    const [first, second, third]: number[] = numbers;
    ```
    
- **Parameter Passing in Functions:**
Destructuring parameters in functions can make function calls more expressive.
    
    ```tsx
    function printPersonInfo({ name, age, city }: Person): void {
      console.log(`Name: ${name}, Age: ${age}, City: ${city}`);
    }
    ```
    
- **Object Property Renaming:**
Renaming variables during destructuring can be useful when dealing with external data.
    
    ```tsx
    const { name: fullName, age: userAge }: Person = person;
    ```
    
- **Default Values:**
Destructuring with default values is helpful when handling properties that may be undefined.
    
    ```tsx
    const { name, age, city = 'Unknown' }: Person = person;
    ```
    

Array and object destructuring enhance code readability and provide a concise syntax for working with arrays and objects. They are widely used in modern JavaScript and TypeScript programming.