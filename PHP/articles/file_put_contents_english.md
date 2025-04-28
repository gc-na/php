<!--
Meta Description: # file_put_contents: The PHP Function for Writing Data to Files ## Synopsis `file_put_contents` is a PHP function that allows developers to write data...
Meta Keywords: file, data, file_put_contents, function, context
-->

# file_put_contents: The PHP Function for Writing Data to Files

## Synopsis
`file_put_contents` is a PHP function that allows developers to write data to a file, either by creating a new file or overwriting an existing one. It is a straightforward and efficient way to handle file writing operations in PHP.

## Documentation

### Purpose
The `file_put_contents` function is designed to write a string to a file. It can create a new file if it does not exist, or overwrite an existing file. This function is particularly useful for saving data from various sources, such as user input, application data, or generated content.

### Usage
The basic syntax of the `file_put_contents` function is as follows:

```php
int file_put_contents(string $filename, mixed $data, int $flags = 0, resource $context = null);
```

- **$filename**: The path to the file where the data will be written.
- **$data**: The data to write, which can be a string, array, or any other type that can be converted to a string.
- **$flags**: Optional. A bitmask of flags that modifies the behavior of the function. Common flags include:
  - `FILE_APPEND`: If this flag is set, the data will be appended to the file instead of overwriting it.
  - `LOCK_EX`: This flag will acquire an exclusive lock on the file while writing to it.
- **$context**: Optional. A valid context resource created with `stream_context_create()`, which can modify the behavior of the file operation.

### Return Value
The function returns the number of bytes written to the file on success, or `false` on failure.

## Examples

### Example 1: Basic Usage
```php
$data = "Hello, World!";
$result = file_put_contents('example.txt', $data);

if ($result === false) {
    echo "Error writing to file.";
} else {
    echo "$result bytes written to file.";
}
```

### Example 2: Appending Data
```php
$data = "\nAppended line.";
$result = file_put_contents('example.txt', $data, FILE_APPEND);

if ($result === false) {
    echo "Error appending to file.";
} else {
    echo "$result bytes appended to file.";
}
```

### Example 3: Writing with Context
```php
$options = [
    'http' => [
        'header' => 'Content-Type: text/plain'
    ]
];
$context = stream_context_create($options);

$data = "This is a test with context.";
$result = file_put_contents('example.txt', $data, 0, $context);

if ($result === false) {
    echo "Error writing to file with context.";
} else {
    echo "$result bytes written to file with context.";
}
```

## Explanation

### Common Pitfalls
- **File Permissions**: Ensure that the script has permission to write to the specified file or directory. If permissions are insufficient, the function will fail.
- **Path Issues**: If the specified path is incorrect or the directory does not exist, `file_put_contents` will fail. Always validate the file path before using it.
- **Data Type**: Ensure the data being written is in a string format. If you provide an array or object, it will be converted to a string representation, which may not be what you intend.
- **Handling Errors**: It’s essential to check the return value for errors, as `file_put_contents` returns `false` on failure.

### Additional Notes
Using the `FILE_APPEND` flag allows you to add content to the end of an existing file without overwriting it. If you need to ensure that the file is not changed by another process while writing, consider using the `LOCK_EX` flag.

## One Line Summary
`file_put_contents` is a PHP function that writes data to a file, allowing for easy creation and modification of files with options for appending data and managing file locks.