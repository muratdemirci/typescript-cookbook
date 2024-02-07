# Installing & Using TypeScript

To install and use TypeScript, you can follow these steps:

### Installation:

1. **Install Node.js:**
    - TypeScript requires Node.js and npm (Node Package Manager). You can download and install them from the official website: [Node.js](https://nodejs.org/)
2. **Install TypeScript globally:**
    - Open your terminal or command prompt and run the following command to install TypeScript globally:
    This command installs the TypeScript compiler globally on your machine.
        
        ```bash
        npm install -g typescript
        ```
        

### Using TypeScript:

1. **Create a TypeScript File:**
    - Create a new file with a `.ts` extension. For example, `app.ts`.
2. **Write TypeScript Code:**
    - Write your TypeScript code in the `.ts` file. TypeScript supports JavaScript syntax along with additional features. For example:
        
        ```tsx
        // app.ts
        function greeter(person: string) {
            return "Hello, " + person;
        }
        
        let user = "John";
        console.log(greeter(user));
        ```
        
3. **Compile TypeScript Code:**
    - Compile the TypeScript code into JavaScript using the TypeScript compiler. Run the following command in the terminal:
    This command generates a corresponding `.js` file. In this case, `app.js`.
        
        ```bash
        tsc app.ts
        ```
        
4. **Run the JavaScript Code:**
    - You can now run the generated JavaScript code using Node.js. For example:
    This will execute the JavaScript code produced by the TypeScript compiler.
        
        ```bash
        node app.js
        ```
        

### Configuration (Optional):

- You can create a `tsconfig.json` file in your project to configure TypeScript settings. This file allows you to specify compiler options, include/exclude files, and more. Here's a basic example:
    
    ```json
    {
      "compilerOptions": {
        "target": "es5",
        "module": "commonjs",
        "strict": true
      }
    }
    ```
    
- After creating a `tsconfig.json` file, you can compile your TypeScript code by simply running `tsc` in the terminal. The compiler will use the configuration settings defined in `tsconfig.json`.

That's it! You've successfully installed TypeScript and created a simple TypeScript project. You can now continue writing and compiling TypeScript code based on your project needs.