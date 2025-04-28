<!--
Meta Description: # Understanding the PHP `list()` Function: A Comprehensive Guide ## Synopsis The `list()` function in PHP is a powerful feature that allows for the as...
Meta Keywords: list, array, php, function, values
-->

# Understanding the PHP `list()` Function: A Comprehensive Guide

## Synopsis
The `list()` function in PHP is a powerful feature that allows for the assignment of multiple variables in a single operation, enabling easier handling of array values.

## Documentation
### Purpose
The `list()` function is primarily used to assign values from an array to a list of variables. It is particularly useful when dealing with indexed arrays, allowing developers to extract values efficiently without needing to access each index individually.

### Usage
The basic syntax of the `list()` function is as follows:

```php
list($var1, $var2, $var3, ...) = $array;
```

Where:
- `$var1`, `$var2`, `$var3`, etc., are the variables that will be assigned values from the array.
- `$array` is the array from which the values will be extracted.

### Details
- The `list()` function only works with numerically indexed arrays (0, 1, 2, ...).
- It is important to note that `list()` resets any internal pointer of the array it is used with, but it does not create a new copy of the array.
- The `list()` function can only be used with arrays and will return `NULL` if used outside of this context.

## Examples
### Basic Example
Here’s a simple example of using `list()` to extract values from an array:

```php
$person = ['John', 'Doe', 30];
list($firstName, $lastName, $age) = $person;

echo $firstName; // Outputs: John
echo $lastName;  // Outputs: Doe
echo $age;       // Outputs: 30
```

### Using `list()` with `each()`
While `each()` has been deprecated in PHP 7.2, it can still illustrate how to use `list()` effectively:

```php
$people = [
    ['John', 'Doe', 30],
    ['Jane', 'Smith', 25],
];

foreach ($people as $person) {
    list($firstName, $lastName, $age) = $person;
    echo "$firstName $lastName is $age years old.\n";
}
```

### Assigning with Gaps
You can skip elements in the array by leaving empty slots in `list()`:

```php
$data = ['Alice', 'Bob', 'Charlie'];
list($first, , $third) = $data;

echo $first; // Outputs: Alice
echo $third; // Outputs: Charlie
```

## Explanation
### Common Pitfalls
- **Non-Indexed Arrays:** Using `list()` on associative arrays will not work as expected. It will only assign values based on the order of the numerical keys, ignoring any string keys.
  
```php
$assocArray = ['name' => 'Alice', 'age' => 25];
list($name, $age) = $assocArray; // $name and $age will be NULL.
```

- **Array Size Mismatch:** If the array has fewer elements than the number of variables specified in `list()`, the extra variables will be assigned `NULL`.

### Additional Notes
- Use `list()` within a `foreach` loop to efficiently unpack array values when iterating over multidimensional arrays.
- The `list()` function is not suitable for associative arrays; consider using a regular assignment instead.

## One Line Summary
The PHP `list()` function allows for convenient assignment of multiple variables from an indexed array in a single operation.