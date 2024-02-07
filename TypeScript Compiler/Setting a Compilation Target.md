# Setting a Compilation Target

## Introduction

In TypeScript, you can set the compilation target to specify the ECMAScript version of the generated JavaScript code. The compilation target is defined using the `target` option in the `tsconfig.json` configuration file. This option ensures that the generated JavaScript code adheres to the specified ECMAScript version.

## Table of Contents

- [1. **Update tsconfig.json:**](#1-update-tsconfigjson)
- [2. **Available Target Options:**](#2-available-target-options)
- [3. **Example Configuration for ES6:**](#3-example-configuration-for-es6)
- [4. **Consider Browser Compatibility:**](#4-consider-browser-compatibility)
- [5. **Check TypeScript Version Compatibility:**](#5-check-typescript-version-compatibility)
- [6. **Run the TypeScript Compiler:**](#6-run-the-typescript-compiler)


### 1. **Update tsconfig.json:**

Open or create the `tsconfig.json` file in the root of your TypeScript project. Add or modify the `"compilerOptions"` section and set the `target` option to the desired ECMAScript version.

For example, if you want to target ECMAScript 5 (ES5):

```json
{
  "compilerOptions": {
    "target": "es5",
    "// other options...": "..."
  },
  "// other settings...": "..."
}
```

### 2. **Available Target Options:**

- **"es3"**: ECMAScript 3
- **"es5"**: ECMAScript 5
- **"es6" or "es2015"**: ECMAScript 2015 (ES6)
- **"es2016"**: ECMAScript 2016
- **"es2017"**: ECMAScript 2017
- **"es2018"**: ECMAScript 2018
- **"es2019"**: ECMAScript 2019
- **"es2020"**: ECMAScript 2020
- **"es2021"**: ECMAScript 2021
- **"esnext"**: Latest ECMAScript version supported by your TypeScript version

### 3. **Example Configuration for ES6:**

```json
{
  "compilerOptions": {
    "target": "es6",
    "// other options...": "..."
  },
  "// other settings...": "..."
}
```

In this example, the `target` is set to "es6," indicating that the generated JavaScript code should follow the ECMAScript 2015 (ES6) standard.

### 4. **Consider Browser Compatibility:**

When setting the compilation target, consider the compatibility requirements of your target environment. For web development, you may want to target a version supported by the majority of your users' browsers.

### 5. **Check TypeScript Version Compatibility:**

Ensure that your TypeScript version supports the selected compilation target. Newer ECMAScript versions may require a more recent TypeScript version for full support.

### 6. **Run the TypeScript Compiler:**

After updating the `tsconfig.json` file, run the TypeScript compiler (`tsc`) to recompile your TypeScript code:

```bash
tsc
```

This will generate JavaScript files in the specified output directory (`"outDir"`) with the specified ECMAScript version.

Setting the compilation target is essential for ensuring compatibility with the intended runtime environment and taking advantage of the features available in the chosen ECMAScript version.