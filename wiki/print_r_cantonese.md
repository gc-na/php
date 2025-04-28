<!--
Meta Description: # PHP 中的 print_r 函數：用於顯示數組和對象的調試工具 ## 簡介 `print_r` 是 PHP 中一個用於輸出變量內容的函數，特別適合用來顯示數組和對象的結構。它對於調試程式碼時查看變量的內容非常有用。 ## 文檔 ### 目的 `print_r` 函數的主要目的是將變量的易讀格式...
Meta Keywords: print_r, php, object, return, array
-->

# PHP 中的 print_r 函數：用於顯示數組和對象的調試工具

## 簡介
`print_r` 是 PHP 中一個用於輸出變量內容的函數，特別適合用來顯示數組和對象的結構。它對於調試程式碼時查看變量的內容非常有用。

## 文檔
### 目的
`print_r` 函數的主要目的是將變量的易讀格式輸出到螢幕，尤其是對於多維數組和對象，讓開發者能夠快速理解變量的結構和內容。

### 用法
函數的基本語法如下：
```php
print_r(mixed $expression, bool $return = false): string|null
```
- **$expression**：要輸出的變量，這可以是任何類型，包括數組、對象、字串等。
- **$return**：一個可選的布爾值，默認為 `false`。若設置為 `true`，將返回變量的內容而不是直接輸出。

### 詳細說明
- 當 `$return` 為 `false` 時，`print_r` 將直接將結果輸出到頁面。
- 若 `$return` 為 `true`，則函數將返回一個字串，這樣可以進一步處理或存儲輸出結果。
- `print_r` 對於多維數組和對象的輸出格式化非常友好，使得視覺上更易於理解。

## 示例
### 基本用法
```php
$array = array('apple', 'banana', 'cherry');
print_r($array);
```
輸出：
```
Array
(
    [0] => apple
    [1] => banana
    [2] => cherry
)
```

### 使用返回值
```php
$object = new stdClass();
$object->name = 'John';
$object->age = 30;

$result = print_r($object, true);
echo $result;
```
輸出：
```
stdClass Object
(
    [name] => John
    [age] => 30
)
```

## 解釋
### 常見問題
- **輸出不完整**：如果變量包含循環引用，`print_r` 可能不會顯示所有內容。
- **格式不如 var_dump 精細**：雖然 `print_r` 較為易讀，但對於需要詳細類型資訊的情況，使用 `var_dump` 可能更合適。
- **在生產環境中使用的風險**：`print_r` 的輸出可能會洩露敏感數據，因此在生產環境中應謹慎使用。

## 總結
`print_r` 是 PHP 中一個方便的函數，用於顯示變量的結構和內容，特別是在調試過程中。