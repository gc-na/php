<!--
Meta Description: # PHP中的array_merge函数详解 ## 概述 `array_merge`是PHP中的一个内置函数，用于将一个或多个数组合并为一个新数组。如果数组中存在相同的字符串键名，则后面的数组值将覆盖前面的值。 ## 文档 ### 功能 `array_merge`函数的主要功能是将多个数组合并成一个...
Meta Keywords: array, array_merge, array1, array2, result
-->

# PHP中的array_merge函数详解

## 概述
`array_merge`是PHP中的一个内置函数，用于将一个或多个数组合并为一个新数组。如果数组中存在相同的字符串键名，则后面的数组值将覆盖前面的值。

## 文档
### 功能
`array_merge`函数的主要功能是将多个数组合并成一个单一的数组。这个函数会按顺序将数组中的元素添加到新数组中，并且会重建数值键名。

### 用法
```php
array array_merge ( array $array1 [, array ...$arrays ] )
```

- **参数**：
  - `$array1`：第一个要合并的数组。
  - `...$arrays`：可选的后续数组，可以传入多个数组进行合并。

- **返回值**：
  - 返回一个新数组，包含了所有输入数组的元素。如果输入数组为空，则返回一个空数组。

### 注意事项
- 如果输入数组中有相同的字符串键名，后面的数组值会覆盖前面的值。
- 数值键名会被重新索引，合并后会从0开始重新排列。

## 示例
### 示例1：基本用法
```php
$array1 = array("a" => "apple", "b" => "banana");
$array2 = array("b" => "berry", "c" => "cherry");

$result = array_merge($array1, $array2);
print_r($result);
```
输出：
```
Array
(
    [a] => apple
    [b] => berry
    [c] => cherry
)
```

### 示例2：合并多个数组
```php
$array1 = array("a" => "apple");
$array2 = array("b" => "banana");
$array3 = array("c" => "cherry");

$result = array_merge($array1, $array2, $array3);
print_r($result);
```
输出：
```
Array
(
    [a] => apple
    [b] => banana
    [c] => cherry
)
```

### 示例3：数组重建索引
```php
$array1 = array(1, 2);
$array2 = array(3, 4);

$result = array_merge($array1, $array2);
print_r($result);
```
输出：
```
Array
(
    [0] => 1
    [1] => 2
    [2] => 3
    [3] => 4
)
```

## 说明
- **常见问题**：使用`array_merge`时，如果您不希望键名被覆盖，可以考虑使用`array_merge_recursive`，该函数会合并相同键名的值为数组。
- **性能考虑**：在处理大数组时，应注意`array_merge`的内存使用情况，因为它会创建一个新的数组，而不是原地修改。
- **空数组**：如果传入的是空数组，`array_merge`将返回一个空数组。

## 一句话总结
`array_merge`是PHP中用于合并多个数组的强大工具，能够处理键名重复和数组重建索引的情况。