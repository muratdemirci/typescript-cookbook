# Understanding TypeScript Core Libs

## Introduction

The core libraries (sometimes referred to as "lib files") are a set of declaration files that provide type information for the standard JavaScript runtime environment and commonly used JavaScript libraries. These declaration files enable TypeScript to understand the types and APIs available in these environments, allowing for improved type checking and autocompletion in your TypeScript code.

## Table of Contents

- [1. **TypeScript Configuration (`tsconfig.json`):**](#1-typescript-configuration-tsconfigjson)
- [2. **Common Core Libraries:**](#2-common-core-libraries)
- [3. **Impact on Type Checking:**](#3-impact-on-type-checking)
- [4. **Targeting Specific Environments:**](#4-targeting-specific-environments)
- [5. **Customizing Core Libraries:**](#5-customizing-core-libraries)
- [6. **Checking Available Libraries:**](#6-checking-available-libraries)
- [7. **Use Case for `"scripthost"`:**](#7-use-case-for-scripthost)


### 1. **TypeScript Configuration (`tsconfig.json`):**

The inclusion of core libraries is specified in the `tsconfig.json` file using the `"lib"` compiler option. The `"lib"` option allows you to include or exclude specific libraries. If you don't explicitly specify `"lib"`, TypeScript will include the default set of libraries based on the target ECMAScript version.

Example of specifying core libraries in `tsconfig.json`:

```json
{
  "compilerOptions": {
    "target": "es5",
    "lib": ["dom", "es2015", "scripthost"]
    // Other compiler options...
  }
}
```

### 2. **Common Core Libraries:**

- **`"dom"`**: Includes the Document Object Model (DOM) types for web development.
- **`"es5"`**: Adds types for ECMAScript 5 features.
- **`"es6"` or `"es2015"`**: Adds types for ECMAScript 2015 (ES6) features.
- **`"esnext"`**: Includes types for the latest ECMAScript features not yet standardized.

### 3. **Impact on Type Checking:**

The core libraries influence type checking by providing type information for the functions, objects, and features available in the specified environments. They help TypeScript understand the types of variables, parameters, and return values, improving the accuracy of type checking.

### 4. **Targeting Specific Environments:**

Depending on your project and deployment environment, you may choose specific core libraries to include. For example, if you are building a web application, including `"dom"` is essential for working with the DOM API.

### 5. **Customizing Core Libraries:**

You can customize the set of core libraries based on your needs. Specifying `"lib": []` in `tsconfig.json` will exclude all default libraries, and you can selectively include only the ones you need.

```json
{
  "compilerOptions": {
    "target": "es6",
    "lib": []
    // Other compiler options...
  }
}
```

### 6. **Checking Available Libraries:**

You can check the available core libraries for a specific TypeScript version in the TypeScript documentation or by consulting the TypeScript source code. The `lib` folder in the TypeScript GitHub repository contains the declaration files for core libraries.

### 7. **Use Case for `"scripthost"`:**

The `"scripthost"` library is sometimes included to support scenarios where TypeScript code runs in non-browser environments (e.g., Node.js) that may lack certain browser-specific APIs.

```json
{
  "compilerOptions": {
    "target": "es6",
    "lib": ["dom", "es2015", "scripthost"]
    // Other compiler options...
  }
}
```

Understanding and configuring TypeScript core libraries are essential for ensuring that your TypeScript code aligns with the target runtime environment and that type checking is accurate and comprehensive.