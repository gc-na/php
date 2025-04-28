<!--
Meta Description: # PHP strpos 函數：字串搜尋的利器 ## 簡介 `strpos` 函數是 PHP 中一個非常有用的字串操作函數，主要用來查找一個字串在另一個字串中第一次出現的位置。此函數在處理字串和進行文本分析時，特別受到開發者的青睞。 ## 文檔 ### 目的 `strpos` 函數的主要目的是返回一...
Meta Keywords: needle, strpos, haystack, php, position
-->

# PHP strpos 函數：字串搜尋的利器

## 簡介
`strpos` 函數是 PHP 中一個非常有用的字串操作函數，主要用來查找一個字串在另一個字串中第一次出現的位置。此函數在處理字串和進行文本分析時，特別受到開發者的青睞。

## 文檔
### 目的
`strpos` 函數的主要目的是返回一個字串在另一個字串中出現的第一個位置（索引），如果未找到則返回 `false`。

### 語法
```php
int|false strpos ( string $haystack , string $needle [, int $offset = 0 ] )
```

### 參數
- **$haystack**：要搜尋的主字串。
- **$needle**：要查找的子字串。
- **$offset**（可選）：開始搜尋的位置，預設為 0。

### 返回值
- 如果找到 `$needle`，返回其在 `$haystack` 中的索引，索引從 0 開始。
- 如果未找到，返回 `false`。

## 範例
### 基本用法
```php
$haystack = "Hello, World!";
$needle = "World";

$position = strpos($haystack, $needle);
if ($position !== false) {
    echo "找到 '$needle' 在位置: $position"; // 輸出: 找到 'World' 在位置: 7
} else {
    echo "'$needle' 未找到";
}
```

### 使用偏移量
```php
$haystack = "Hello, World!";
$needle = "o";

$position = strpos($haystack, $needle, 5);
if ($position !== false) {
    echo "找到 '$needle' 在位置: $position"; // 輸出: 找到 'o' 在位置: 8
} else {
    echo "'$needle' 未找到";
}
```

## 解釋
使用 `strpos` 時需要注意以下幾點：
1. **返回值類型**：因為 `strpos` 可能返回 0（表示字串的開始位置），所以在檢查返回值時應該使用嚴格比較運算符 `!==`，而非 `!=`，以避免誤判。
2. **區分大小寫**：`strpos` 是區分大小寫的，因此 "hello" 和 "Hello" 會被認為是不同的字串。
3. **偏移量的使用**：當使用偏移量時，請確保其不超出字串的長度，否則將不會返回任何結果。

## 簡潔總結
`strpos` 函數是用於查找字串在另一字串中位置的重要工具，並且在 PHP 中非常常見。