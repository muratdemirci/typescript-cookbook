# Compiling the Entire Project / Multiple Files

## Introduction

When compiling a TypeScript project that consists of multiple files, you can use the TypeScript compiler (`tsc`) to process the entire project. 

## Table of Contents

- [1. **Organize Project Structure:**](#1-organize-project-structure)
- [2. **Create tsconfig.json:**](#2-create-tsconfigjson)
- [3. **Run the TypeScript Compiler:**](#3-run-the-typescript-compiler)
- [4. **Check the Output:**](#4-check-the-output)
- [5. **Run Compiled JavaScript:**](#5-run-compiled-javascript)
- [6. **Watch Mode (Optional):**](#6-watch-mode-optional)


### 1. **Organize Project Structure:**

Ensure that your TypeScript files are organized in a logical directory structure. It's common to use a dedicated folder (e.g., `src`) for your TypeScript source files.

Example project structure:

```
my-project/
├── src/
│   ├── main.ts
│   ├── utils/
│   │   ├── math.ts
│   │   └── string.ts
│   └── components/
│       ├── button.ts
│       └── input.ts
└── tsconfig.json
```

### 2. **Create tsconfig.json:**

Create a `tsconfig.json` file in the root of your project to configure TypeScript compilation options. Here's a minimal example:

```json
{
  "compilerOptions": {
    "target": "es5",
    "module": "commonjs",
    "outDir": "./dist",
    "rootDir": "./src",
    "strict": true
  },
  "include": ["src/**/*.ts"],
  "exclude": ["node_modules"]
}
```

- `"outDir"`: Specifies the output directory for compiled JavaScript files.
- `"rootDir"`: Indicates the root directory of TypeScript source files.
- `"include"`: An array of file patterns to include in compilation.
- `"exclude"`: An array of file patterns to exclude from compilation.

### 3. **Run the TypeScript Compiler:**

Open a terminal, navigate to the project's root directory, and run the TypeScript compiler using the `tsc` command:

```bash
tsc
```

This command compiles the entire project based on the settings in the `tsconfig.json` file.

### 4. **Check the Output:**

After compilation, you should see the generated JavaScript files in the specified `outDir` (e.g., `dist` in the example). The directory structure within `outDir` mirrors the structure of your `src` directory.

Example output:

```
my-project/
├── dist/
│   ├── main.js
│   ├── utils/
│   │   ├── math.js
│   │   └── string.js
│   └── components/
│       ├── button.js
│       └── input.js
└── tsconfig.json
```

### 5. **Run Compiled JavaScript:**

You can now run the compiled JavaScript files using the appropriate runtime environment (e.g., Node.js for server-side code or a browser for client-side code).

For example, if using Node.js:

```bash
node dist/main.js
```

### 6. **Watch Mode (Optional):**

To enable continuous compilation in watch mode (recompiling on file changes), use the `--watch` flag:

```bash
tsc --watch
```

This is useful during development when you want the compiler to automatically update the output when you save changes to your TypeScript files.

By following these steps, you can compile a TypeScript project with multiple files. Adjust the `tsconfig.json` settings based on your project's requirements.