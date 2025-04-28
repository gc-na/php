<!--
Meta Description: # Understanding `include_once` in PHP: A Comprehensive Guide ## Synopsis The `include_once` statement in PHP is a crucial feature that allows develope...
Meta Keywords: php, include_once, file, included, will
-->

# Understanding `include_once` in PHP: A Comprehensive Guide

## Synopsis
The `include_once` statement in PHP is a crucial feature that allows developers to include and evaluate a specified file during the execution of a script, ensuring that the file is included only once, even if called multiple times.

## Documentation
### Purpose
The primary purpose of `include_once` is to prevent the redeclaration of functions, classes, or variables that may occur if a file is included multiple times. This is especially useful in large applications where files may be included in multiple locations.

### Usage
The syntax for `include_once` is as follows:

```php
include_once 'filename.php';
```

- **filename.php**: The path to the PHP file you want to include. This can be a relative or absolute path.

When a script containing `include_once` is executed, PHP will check if the specified file has already been included. If it has not, PHP will include it; if it has, PHP will skip it, preventing any re-declarations.

### Details
- **Error Handling**: If the specified file cannot be found, `include_once` will emit a warning but allow the script to continue executing. To stop execution entirely, consider using `require_once`.
- **Performance**: Using `include_once` can slightly impact performance when compared to `include`, as PHP must check if the file has already been included. However, this is generally negligible and can save time and resources in larger applications.

## Examples
### Basic Usage Example
Here’s a simple example of using `include_once`:

**File: config.php**
```php
<?php
$databaseHost = 'localhost';
$databaseUser = 'root';
$databasePass = '';
$databaseName = 'test_db';
?>
```

**File: main.php**
```php
<?php
include_once 'config.php';
include_once 'config.php'; // This will be ignored

echo $databaseHost; // Outputs: localhost
?>
```

In this example, `config.php` is included twice, but the variables are defined only once due to `include_once`.

### Including Functions
You can also use `include_once` to include files that contain function definitions:

**File: functions.php**
```php
<?php
function greet() {
    return "Hello, World!";
}
?>
```

**File: index.php**
```php
<?php
include_once 'functions.php';
include_once 'functions.php'; // This will be ignored

echo greet(); // Outputs: Hello, World!
?>
```

## Explanation
### Common Pitfalls
- **File Path Issues**: Ensure that the path to the file is correct. A common pitfall is using a relative path that does not resolve correctly based on the script's execution context.
- **Namespace Conflicts**: If the included file contains classes or functions with the same name as those in other files, you may encounter redeclaration errors. Consider using namespaces to avoid these conflicts.
- **Misunderstanding Differences**: Some developers confuse `include_once` with `require_once`. While both prevent multiple inclusions, `require_once` will halt script execution on failure to include the file, while `include_once` will only issue a warning.

### Additional Notes
- **Scope**: Variables defined within an included file are available in the scope where `include_once` was called.
- **Best Practices**: It is advisable to use `include_once` for configuration files, libraries, and files that contain functions or classes to maintain clean and organized code.

## One Line Summary
`include_once` in PHP is a powerful statement that ensures a file is included only once during script execution, helping avoid function and variable redeclaration issues.