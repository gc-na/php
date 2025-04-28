<!--
Meta Description: # Understanding `const` in PHP: Definition, Usage, and Best Practices ## Synopsis The `const` keyword in PHP is used to define constants, which are id...
Meta Keywords: const, constants, constant, php, can
-->

# Understanding `const` in PHP: Definition, Usage, and Best Practices

## Synopsis
The `const` keyword in PHP is used to define constants, which are identifiers for simple values that cannot be changed during the script's execution. Constants provide a way to store fixed values that remain consistent throughout the code, enhancing maintainability and readability.

## Documentation
### Purpose
The `const` keyword allows developers to create constant values that can be accessed globally throughout the script. Unlike variables, constants are immutable, meaning their values cannot be altered once defined. This feature is particularly useful for defining configuration values, error codes, or any other fixed data that should not change.

### Usage
To define a constant using `const`, follow this syntax:

```php
const CONSTANT_NAME = value;
```

- `CONSTANT_NAME`: The name of the constant, which must adhere to the naming conventions (uppercase letters are typically used).
- `value`: The fixed value assigned to the constant, which can be a string, integer, float, boolean, or array.

Constants defined using `const` are automatically global and can be accessed from any scope without needing to use the `global` keyword.

### Details
- Constants can be defined at any level: inside classes, functions, or globally.
- When defining constants within a class, you can use the `const` keyword followed by a valid name and value.
- The value of a constant must be a constant expression, which means it cannot be a variable or the result of a function call.

## Examples
### Basic Usage
1. **Defining a Constant:**
   ```php
   const PI = 3.14;
   echo PI; // Outputs: 3.14
   ```

2. **Using Constants in a Class:**
   ```php
   class Math {
       const E = 2.718;
   }
   echo Math::E; // Outputs: 2.718
   ```

3. **Defining a Constant Array:**
   ```php
   const COLORS = ['red', 'green', 'blue'];
   echo COLORS[1]; // Outputs: green
   ```

### Accessing Constants
Constants are accessed without the `$` symbol:
```php
echo PI; // Outputs: 3.14
```

## Explanation
### Common Pitfalls
- **Case Sensitivity**: While constant names are case-sensitive, it is a common convention to define them in uppercase to distinguish them easily from variables.
- **Immutable Nature**: Attempting to change the value of a constant after it has been defined will result in a fatal error. For example:
  ```php
  const MAX_VALUE = 100;
  MAX_VALUE = 200; // Fatal error: Cannot redefine constant MAX_VALUE
  ```

### Additional Notes
- Unlike the `define()` function, which can define constants at runtime, `const` must be defined at compile time.
- `const` can only be used to define scalar values and arrays but cannot be used for resource types or objects.

## One Line Summary
The `const` keyword in PHP is used to define immutable constants that can be accessed globally within a script, enhancing code readability and maintainability.