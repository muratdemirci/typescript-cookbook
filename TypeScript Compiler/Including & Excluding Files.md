# Including & Excluding Files

## Introduction

You can control which files are included or excluded from compilation using the `"include"` and `"exclude"` options in the `tsconfig.json` configuration file.

### Including Files:

The `"include"` option specifies an array of file globs that determine which files should be included in the compilation. Here's an example:

```json
{
  "compilerOptions": {
    // Compiler options...
  },
  "include": [
    "src/**/*.ts",
    "tests/**/*.ts"
  ]
}
```

In this example, TypeScript will include all `.ts` files under the `src` and `tests` directories and their subdirectories in the compilation process.

### Excluding Files:

The `"exclude"` option specifies an array of file globs for files that should be excluded from compilation. Here's an example:

```json
{
  "compilerOptions": {
    // Compiler options...
  },
  "exclude": [
    "node_modules",
    "build"
  ]
}
```

In this example, TypeScript will exclude all files under the `node_modules` and `build` directories from the compilation.

### Using Both `"include"` and `"exclude"`:

You can use both `"include"` and `"exclude"` options together. When both options are specified, TypeScript first includes files based on the `"include"` patterns and then excludes files based on the `"exclude"` patterns. Here's an example:

```json
{
  "compilerOptions": {
    // Compiler options...
  },
  "include": [
    "src/**/*.ts",
    "tests/**/*.ts"
  ],
  "exclude": [
    "node_modules",
    "build"
  ]
}
```

In this example, TypeScript includes files matching the `"include"` patterns but excludes files matching the `"exclude"` patterns.

### Using "files" Option:

Alternatively, you can use the `"files"` option to explicitly list the files that should be included. This option overrides both `"include"` and `"exclude"`. Here's an example:

```json
{
  "compilerOptions": {
    // Compiler options...
  },
  "files": [
    "src/main.ts",
    "src/utils/math.ts",
    "tests/test1.ts"
  ]
}
```

In this example, TypeScript will only compile the files specified in the `"files"` array.

Choose the approach that best fits your project's organization and requirements. The combination of `"include"`, `"exclude"`, and `"files"` options gives you flexibility in controlling which files are part of the TypeScript compilation process.