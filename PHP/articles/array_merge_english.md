<!--
Meta Description: # Comprehensive Guide to PHP array_merge: Merging Arrays Efficiently ## Synopsis The `array_merge` function in PHP is a powerful tool used to merge on...
Meta Keywords: arrays, array, keys, array_merge, php
-->

# Comprehensive Guide to PHP array_merge: Merging Arrays Efficiently

## Synopsis
The `array_merge` function in PHP is a powerful tool used to merge one or more arrays into a single array, with duplicate keys overwritten by subsequent values. This function is essential for developers looking to combine data effectively in their applications.

## Documentation
### Purpose
`array_merge` serves to combine multiple arrays into one. When merging, if two or more arrays have the same string keys, the values from the later arrays will overwrite those from the earlier ones. Numeric keys will be re-indexed.

### Usage
The basic syntax for `array_merge` is as follows:

```php
array array_merge(array $array1, array ...$arrays)
```

- **$array1**: The first array to merge.
- **$arrays**: Additional arrays to merge with the first array. You can pass any number of arrays.

### Return Value
The function returns a new array containing all the elements from the input arrays. If the input arrays are empty, an empty array is returned.

### Example
Here is a simple example to demonstrate how `array_merge` works:

```php
$array1 = ['a' => 'apple', 'b' => 'banana'];
$array2 = ['b' => 'blueberry', 'c' => 'cherry'];
$array3 = ['d' => 'date'];

$result = array_merge($array1, $array2, $array3);
print_r($result);
```

**Output:**
```
Array
(
    [a] => apple
    [b] => blueberry
    [c] => cherry
    [d] => date
)
```

In this example, the value of key 'b' is overwritten by the value from `$array2`.

## Explanation
### Common Pitfalls
1. **Overwriting Keys**: As noted, if the same key exists in multiple arrays, only the last occurrence will be kept. This can lead to unexpected results if not properly managed.
  
2. **Re-indexing Numeric Keys**: When merging arrays with numeric keys, `array_merge` will renumber the keys in the resulting array. This can be problematic if the original keys are important.

3. **Handling Non-Array Inputs**: Passing non-array variables to `array_merge` will lead to a warning and may result in unexpected behavior.

### Additional Notes
- To maintain keys when merging arrays, consider using `array_replace` or `array_replace_recursive` instead.
- The function is best used for flat arrays; be cautious when merging multi-dimensional arrays as it may not yield the desired structure without additional handling.

## One Line Summary
The `array_merge` function in PHP combines multiple arrays into one, prioritizing later values for duplicate keys while re-indexing numeric keys.