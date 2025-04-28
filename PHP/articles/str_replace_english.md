<!--
Meta Description: # PHP str_replace: The Ultimate Guide to String Replacement ## Synopsis `str_replace` is a powerful PHP function used to search for specific substring...
Meta Keywords: string, str_replace, search, php, function
-->

# PHP str_replace: The Ultimate Guide to String Replacement

## Synopsis
`str_replace` is a powerful PHP function used to search for specific substrings within a string and replace them with new substrings, making it an essential tool for string manipulation in PHP applications.

## Documentation
### Purpose
The `str_replace` function replaces all occurrences of a search string with a replacement string within a given input string. It is widely used in scenarios such as data sanitization, formatting, and text replacement.

### Usage
The basic syntax of `str_replace` is as follows:

```php
str_replace(mixed $search, mixed $replace, mixed $subject, int $count = null): mixed
```

#### Parameters
- **$search**: The value or values to search for. This can be a string or an array of strings.
- **$replace**: The value or values to replace the searched string(s) with. This can also be a string or an array.
- **$subject**: The input string or an array of strings in which replacements should be performed.
- **$count** (optional): If passed, this variable will hold the number of replacements made.

#### Return Value
The `str_replace` function returns the modified string (or array of strings) after performing the replacements.

### Example
Here are some basic usage examples of `str_replace`:

```php
// Example 1: Basic String Replacement
$text = "Hello World!";
$modifiedText = str_replace("World", "PHP", $text);
echo $modifiedText; // Output: Hello PHP!

// Example 2: Replacing Multiple Values
$text = "The quick brown fox jumps over the lazy dog.";
$search = array("quick", "fox", "dog");
$replace = array("slow", "cat", "mouse");
$modifiedText = str_replace($search, $replace, $text);
echo $modifiedText; // Output: The slow brown cat jumps over the lazy mouse.

// Example 3: Using count parameter
$text = "Hello, Hello, Hello!";
$count = 0;
$modifiedText = str_replace("Hello", "Hi", $text, $count);
echo $modifiedText; // Output: Hi, Hi, Hi!
echo $count; // Output: 3
```

## Explanation
### Common Pitfalls
1. **Data Types**: Ensure that the types of `$search` and `$replace` match. If you use arrays for either, the function will map replacements based on the index.
2. **Case Sensitivity**: The `str_replace` function is case-sensitive. To perform case-insensitive replacements, use `str_ireplace`.
3. **Multiple Replacements**: If `$search` and `$replace` are arrays of different lengths, only the replacements up to the length of the shorter array will be executed.
4. **Non-String Inputs**: The function may produce unexpected results or warnings if non-string data types are passed as the `$subject`.

### Additional Notes
- Using `str_replace` on large strings or large datasets may affect performance, so consider using it thoughtfully in high-load scenarios.
- This function is ideal for simple text replacements; for more complex manipulation, consider using regular expressions with `preg_replace`.

## One Line Summary
`str_replace` is a PHP function that efficiently replaces all occurrences of a specified substring within a string or array with a new substring.