<!--
Meta Description: # PHP 的 array_merge 函數：陣列合併的最佳利器 ## 概述 `array_merge` 是 PHP 中一個強大的內建函數，用於合併多個陣列，將它們整合成一個新的陣列，並保留所有元素的順序。 ## 文檔 ### 目的 `array_merge` 函數的主要目的是將兩個或多個陣列合併為...
Meta Keywords: array_merge, array, php, array1, apple
-->

# PHP 的 array_merge 函數：陣列合併的最佳利器

## 概述
`array_merge` 是 PHP 中一個強大的內建函數，用於合併多個陣列，將它們整合成一個新的陣列，並保留所有元素的順序。

## 文檔
### 目的
`array_merge` 函數的主要目的是將兩個或多個陣列合併為一個單一的陣列。此函數特別適合用於需要將多個資料集整合的場合，例如資料庫查詢結果的組合。

### 使用方法
```php
array array_merge ( array $array1 [, array $... ] )
```

- **參數**:
  - `$array1`：要合併的第一個陣列。
  - `...`：可選的其他陣列，可以傳遞任意數量的陣列作為參數。

- **返回值**：
  - 返回合併後的陣列。如果沒有任何陣列被傳遞，則返回一個空陣列。

### 詳細說明
- 若合併的陣列中有相同的鍵，後面的陣列的值將會覆蓋前面的值。
- 此函數會重新索引數字鍵的陣列，確保合併後的陣列鍵是連續的整數。
- 如果某個陣列是關聯陣列，則合併後的關聯陣列鍵會保持不變，但後面陣列的相同鍵將覆蓋前面陣列的值。

## 範例
### 基本用法
```php
$array1 = array("a" => "apple", "b" => "banana");
$array2 = array("b" => "blueberry", "c" => "cherry");
$result = array_merge($array1, $array2);

print_r($result);
```
**輸出**:
```
Array
(
    [a] => apple
    [b] => blueberry
    [c] => cherry
)
```

### 數字索引的合併
```php
$array1 = array("apple", "banana");
$array2 = array("cherry", "date");
$result = array_merge($array1, $array2);

print_r($result);
```
**輸出**:
```
Array
(
    [0] => apple
    [1] => banana
    [2] => cherry
    [3] => date
)
```

## 解釋
### 常見陷阱與注意事項
- 當合併數字鍵的陣列時，`array_merge` 會重新編排鍵，這可能會導致預期之外的結果。
- 如果需要保留原有的鍵名，建議使用 `array_merge_recursive`，但請注意，這會合併相同鍵的值為陣列，而不是覆蓋。
- 使用 `array_merge` 時，如果沒有傳遞任何陣列，會返回一個空的陣列，這一點需要特別留意。

## 總結
`array_merge` 是 PHP 中用於合併多個陣列的有效工具，能夠簡單地將多個資料集整合為一個新的陣列。