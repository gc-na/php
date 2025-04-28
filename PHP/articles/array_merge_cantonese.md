<!--
Meta Description: # PHP array_merge 函數詳解：合併數組的最佳方法 ## 簡介 `array_merge` 函數是一個用於合併一個或多個數組的 PHP 函數。它可以將多個數組合併為一個新數組，並且在合併過程中會自動重新索引數字鍵。 ## 文檔 ### 目的 `array_merge` 的主要目的是將多...
Meta Keywords: array_merge, php, array1, array, array2
-->

# PHP array_merge 函數詳解：合併數組的最佳方法

## 簡介
`array_merge` 函數是一個用於合併一個或多個數組的 PHP 函數。它可以將多個數組合併為一個新數組，並且在合併過程中會自動重新索引數字鍵。

## 文檔
### 目的
`array_merge` 的主要目的是將多個數組合併成一個，對於處理和操作數據時非常有用。

### 使用方法
```php
array_merge(array $array1, array ...$arrays): array
```

- **參數**：
  - `$array1`：第一個要合併的數組。
  - `$arrays`：一個或多個要合併的數組（可以是多個數組參數）。
  
- **返回值**：
  - 返回合併後的新數組。如果參數中有任何非數組類型，則將其視為數組。

### 詳細說明
- 當數組中有相同的字符串鍵時，後面的值會覆蓋前面的值。
- 數字鍵會重新索引，最終的結果是從 0 開始的連續索引。

## 範例
### 基本用法
```php
$array1 = ['a' => 'apple', 'b' => 'banana'];
$array2 = ['b' => 'blueberry', 'c' => 'cherry'];
$array3 = ['d' => 'date'];

$result = array_merge($array1, $array2, $array3);
print_r($result);
```
輸出：
```
Array
(
    [a] => apple
    [b] => blueberry
    [c] => cherry
    [0] => date
)
```

### 合併數字鍵
```php
$array1 = [1, 2, 3];
$array2 = [4, 5];

$result = array_merge($array1, $array2);
print_r($result);
```
輸出：
```
Array
(
    [0] => 1
    [1] => 2
    [2] => 3
    [3] => 4
    [4] => 5
)
```

## 解釋
### 常見問題
- **覆蓋行為**：當鍵名重複時，後面的值會覆蓋之前的值。這在合併數組時需特別注意。
- **非數組參數**：如果傳入非數組類型，`array_merge` 會將其視為空數組而不會引發錯誤。

### 注意事項
- `array_merge` 只對數組有效，不支持其他數據類型。在使用前，最好確保所有輸入都是數組。
- 合併的數組會被重新索引，因此如果需要保留原有的索引，請考慮使用其他函數，如 `array_replace`。

## 總結
`array_merge` 是一個簡單而強大的工具，用於合併 PHP 數組，尤其在需要整合多個數據源時極為方便。