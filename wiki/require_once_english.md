<!--
Meta Description: # Understanding `require_once` in PHP: A Comprehensive Guide ## Synopsis `require_once` is a PHP construct used to include and evaluate a specified fi...
Meta Keywords: php, require_once, file, include, functions
-->

# Understanding `require_once` in PHP: A Comprehensive Guide

## Synopsis
`require_once` is a PHP construct used to include and evaluate a specified file during runtime. It ensures that the file is included only once, preventing redeclaration errors and improving code organization.

## Documentation
### Purpose
The `require_once` statement is designed to include a specified PHP file, allowing developers to reuse code effectively. It checks if the file has already been included; if it has, the inclusion is skipped. This feature is especially useful for including libraries, functions, or class definitions without risking multiple inclusions or conflicts.

### Usage
The syntax for using `require_once` is as follows:

```php
require_once 'path/to/file.php';
```

- **File Path**: The path to the PHP file you want to include. This can be a relative or absolute path.
- **Return Value**: Unlike `require`, if the file cannot be found, `require_once` will produce a fatal error and halt the script's execution.

### Details
- **File Inclusion**: `require_once` executes the code within the specified file, making its functions, classes, and variables available in the current script.
- **Error Handling**: If the specified file is not found, a fatal error will be thrown. Unlike `include_once`, which generates a warning and allows the script to continue, `require_once` enforces strict error handling.
- **Performance**: By preventing multiple inclusions, `require_once` can enhance performance, especially in larger applications where the same files are referenced multiple times.

## Examples
### Basic Example 1: Including a Configuration File

```php
// config.php
$databaseHost = 'localhost';
$databaseUser = 'root';
$databasePass = '';
$databaseName = 'test_db';

// main.php
require_once 'config.php';
echo $databaseHost; // Outputs: localhost
```

### Basic Example 2: Including a Class Definition

```php
// MyClass.php
class MyClass {
    public function sayHello() {
        return "Hello, World!";
    }
}

// main.php
require_once 'MyClass.php';
$instance = new MyClass();
echo $instance->sayHello(); // Outputs: Hello, World!
```

### Basic Example 3: Preventing Multiple Inclusions

```php
// functions.php
function myFunction() {
    return "I'm a function!";
}

// main.php
require_once 'functions.php';
require_once 'functions.php'; // This will not include functions.php again
echo myFunction(); // Outputs: I'm a function!
```

## Explanation
### Common Pitfalls
- **File Not Found**: Always ensure the file path is correct; a wrong path will lead to a fatal error.
- **Circular Dependencies**: Be cautious about circular dependencies, where two files include each other, as this can lead to issues in code execution.
- **Case Sensitivity**: File names are case-sensitive on some operating systems (like Linux), so ensure the case matches.

### Gotchas
- **Performance Considerations**: While `require_once` is generally more efficient than multiple `require` calls, unnecessary use can still lead to performance issues. Only use it when needed.
- **Inconsistent Behavior**: If you switch between `require`, `require_once`, and `include`, be conscious of how each handles errors and affects script execution.

## One Line Summary
`require_once` is a PHP statement that includes a specified file only once, preventing redeclaration errors and ensuring clean code reuse.