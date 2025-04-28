<!--
Meta Description: # PHP 的 str_replace 函數：字串替換的強大工具 ## 簡介 `str_replace` 是 PHP 中一個用於字串替換的內建函數，能夠快速且有效地將指定的字串替換為另一個字串。這個函數在處理字串時非常有用，尤其在需要修改或清理資料時。 ## 文檔 ### 目的 `str_repla...
Meta Keywords: str_replace, php, search, replace, originalstring
-->

# PHP 的 str_replace 函數：字串替換的強大工具

## 簡介
`str_replace` 是 PHP 中一個用於字串替換的內建函數，能夠快速且有效地將指定的字串替換為另一個字串。這個函數在處理字串時非常有用，尤其在需要修改或清理資料時。

## 文檔
### 目的
`str_replace` 函數的主要目的是在字串中查找指定的字串並替換為另一個字串。這個功能在資料處理、文本分析以及用戶輸入的清理等場合中非常常見。

### 用法
`str_replace` 的基本語法如下：

```php
str_replace(mixed $search, mixed $replace, mixed $subject, mixed &$count = null): mixed
```

#### 參數
- **$search**: 要查找的字串或字串陣列。
- **$replace**: 用於替換的字串或字串陣列。
- **$subject**: 要進行替換的字串或字串陣列。
- **$count** (可選): 如果提供，這個參數會被填充為進行替換的次數。

#### 返回值
此函數返回替換後的字串。如果 `$subject` 是陣列，則返回一個包含替換後字串的陣列。

## 範例
以下是一些 `str_replace` 的基本使用範例：

### 範例 1：簡單字串替換
```php
$originalString = "Hello World!";
$search = "World";
$replace = "PHP";
$result = str_replace($search, $replace, $originalString);
echo $result; // 輸出: Hello PHP!
```

### 範例 2：多重替換
```php
$originalString = "I love dogs and cats.";
$search = array("dogs", "cats");
$replace = array("birds", "fish");
$result = str_replace($search, $replace, $originalString);
echo $result; // 輸出: I love birds and fish.
```

### 範例 3：計算替換次數
```php
$originalString = "The quick brown fox jumps over the lazy dog.";
$search = "o";
$replace = "0";
$count = 0;
$result = str_replace($search, $replace, $originalString, $count);
echo $result; // 輸出: The quick br0wn f0x jumps 0ver the lazy d0g.
echo $count; // 輸出: 3
```

## 解釋
使用 `str_replace` 時，應注意以下幾點：
1. **大小寫敏感**: `str_replace` 是大小寫敏感的，這意味著 "hello" 和 "Hello" 會被視為不同的字串。
2. **陣列支持**: 如果 `$search` 和 `$replace` 都是陣列，則它們的長度必須相同，否則將導致不預期的結果。
3. **無法處理正則表達式**: 若需要使用正則表達式進行更複雜的替換，應考慮使用 `preg_replace` 函數。

## 一句總結
`str_replace` 是 PHP 中用於快速替換字串的函數，適合處理簡單的字串替換需求。