<!--
Meta Description: # PHP `explode` Function: A Comprehensive Guide ## Synopsis The `explode` function in PHP is used to split a string into an array based on a specified...
Meta Keywords: string, array, explode, delimiter, php
-->

# PHP `explode` Function: A Comprehensive Guide

## Synopsis
The `explode` function in PHP is used to split a string into an array based on a specified delimiter, making it a fundamental tool for string manipulation in PHP programming.

## Documentation
### Purpose
The `explode` function is designed to break a string into smaller parts, or "tokens," using a specified delimiter. This is particularly useful when handling strings that contain multiple values separated by a common character, such as commas, spaces, or slashes.

### Usage
The basic syntax of the `explode` function is as follows:

```php
array explode(string $delimiter, string $string, int $limit = PHP_INT_MAX);
```

- **$delimiter**: The boundary string at which the `string` will be split.
- **$string**: The input string to be split.
- **$limit** (optional): If specified, it determines the maximum number of array elements to return. The last element will contain the rest of the string.

### Return Value
The function returns an array of strings created by splitting the input string. If the delimiter is not found in the string, the returned array will contain a single element (the original string).

## Examples
### Basic Example
```php
$input = "apple,banana,cherry";
$result = explode(",", $input);
print_r($result);
```
**Output:**
```
Array
(
    [0] => apple
    [1] => banana
    [2] => cherry
)
```

### With Limit
```php
$input = "one,two,three,four";
$result = explode(",", $input, 2);
print_r($result);
```
**Output:**
```
Array
(
    [0] => one
    [1] => two,three,four
)
```

### Without Delimiter Found
```php
$input = "hello world";
$result = explode(",", $input);
print_r($result);
```
**Output:**
```
Array
(
    [0] => hello world
)
```

## Explanation
### Common Pitfalls
- **Empty Delimiter**: If the delimiter is an empty string, `explode` will throw a warning and return false. Always ensure that the delimiter is not empty.
- **Limit Parameter**: When using the limit parameter, the last element of the returned array will contain the unprocessed remainder of the string, which can sometimes lead to unexpected results if not handled correctly.
- **Whitespace Handling**: If the delimiter is followed or preceded by whitespace, the resulting array may contain empty strings. For example, `explode(", ", "one, two, three")` will produce an array with elements that may have leading or trailing spaces.

### Additional Notes
- `explode` is case-sensitive, meaning that it distinguishes between "A" and "a". 
- The returned array from `explode` is numerically indexed and can be manipulated using standard array functions in PHP.

## One Line Summary
The `explode` function in PHP splits a string into an array by a specified delimiter, essential for effective string manipulation.