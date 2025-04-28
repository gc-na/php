<!--
Meta Description: # PHP `print`: A Comprehensive Guide to Outputting Data ## Synopsis The `print` construct in PHP is a language construct used to output data to the sc...
Meta Keywords: print, php, output, construct, used
-->

# PHP `print`: A Comprehensive Guide to Outputting Data

## Synopsis
The `print` construct in PHP is a language construct used to output data to the screen. It is a simple and effective way to display strings, variables, and formatted text in web applications.

## Documentation
The `print` construct is one of the most commonly used methods for outputting information in PHP. Unlike functions, `print` is a construct, which means it can be used without parentheses. It always returns 1, making it useful in expressions.

### Purpose
The primary purpose of `print` is to send output to the user, typically in the context of a web page. It can handle strings, variables, and even concatenated expressions.

### Usage
The basic syntax of `print` is as follows:

```php
print(expression);
```

Where `expression` can be a string, variable, or combination thereof.

### Details
- **Return Value**: `print` always returns 1, allowing it to be used in expressions.
- **Type of Output**: `print` outputs a string. If you attempt to print an array or object, PHP will issue a notice.
- **Performance**: `print` is marginally slower than `echo`, but the difference is negligible for most applications.

## Examples
### Basic Example
```php
<?php
print "Hello, World!";
?>
```
Output:
```
Hello, World!
```

### Using Variables
```php
<?php
$name = "John Doe";
print "Hello, " . $name . "!";
?>
```
Output:
```
Hello, John Doe!
```

### Printing Multiple Lines
```php
<?php
print "Line 1\n";
print "Line 2\n";
?>
```
Output:
```
Line 1
Line 2
```

### Using `print` in an Expression
```php
<?php
$result = print "This is printed and returns: ";
echo $result; // Outputs: 1
?>
```

## Explanation
While `print` is straightforward, there are a few common pitfalls to be aware of:

- **Return Value Confusion**: Since `print` returns an integer (1), it can lead to confusion if used in conditional statements or complex expressions.
- **Error Handling**: If you attempt to print an array or object, PHP will generate a notice about the invalid type. It's essential to ensure that only strings or compatible types are passed to `print`.
- **Concatenation**: When using concatenation with `print`, remember to use the dot operator `.` correctly to avoid syntax errors.

## One Line Summary
The `print` construct in PHP is a simple way to output strings and variables to the screen, returning 1 and allowing for use in expressions.