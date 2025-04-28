<!--
Meta Description: # PHP 的 return 關鍵字：功能、用法及範例 ## 概述 `return` 是 PHP 中用於從函數返回值的關鍵字。它允許函數在執行結束時將計算結果或狀態傳遞回函數的調用者。 ## 文檔 `return` 關鍵字的主要目的是結束函數的執行並返回一個值。當函數被調用時，執行流程會進入函數體內...
Meta Keywords: return, php, function, value, null
-->

# PHP 的 return 關鍵字：功能、用法及範例

## 概述
`return` 是 PHP 中用於從函數返回值的關鍵字。它允許函數在執行結束時將計算結果或狀態傳遞回函數的調用者。

## 文檔
`return` 關鍵字的主要目的是結束函數的執行並返回一個值。當函數被調用時，執行流程會進入函數體內，並在遇到 `return` 語句時返回指定的值，然後退出函數。

### 用法
```php
function functionName() {
    // 函數邏輯
    return $value; // 返回值
}
```
在以上的示例中，`$value` 可以是任何類型的數據，包括整數、浮點數、字符串、數組或對象。

### 詳細說明
- `return` 語句可以在函數的任何地方使用，但當函數執行到 `return` 時，函數將終止執行，並返回指定的值。
- 若不使用 `return`，函數將默認返回 `null`。
- 在一個函數中可以使用多個 `return` 語句，但只有一個會被執行，具體取決於條件邏輯。
- 使用 `return` 返回的值可以被賦值給變數，以便在函數外部使用。

## 範例
以下是幾個使用 `return` 的基本範例：

### 範例 1：返回整數
```php
function add($a, $b) {
    return $a + $b; // 返回兩數的和
}

$result = add(5, 10);
echo $result; // 輸出：15
```

### 範例 2：返回字符串
```php
function greet($name) {
    return "Hello, " . $name; // 返回問候語
}

$message = greet("Alice");
echo $message; // 輸出：Hello, Alice
```

### 範例 3：返回陣列
```php
function getColors() {
    return ["red", "green", "blue"]; // 返回顏色陣列
}

$colors = getColors();
print_r($colors); // 輸出：Array ( [0] => red [1] => green [2] => blue )
```

## 解釋
- **常見陷阱**：在函數中如果有多個 `return` 語句，可能會導致程式邏輯混亂，建議清晰地設計條件來控制哪些路徑會返回值。
- **注意事項**：如果函數中沒有 `return` 語句，函數將返回 `null`，這可能會導致調用者未預期的行為。
- **類型提示**：在 PHP 7 及以上版本，可以為函數添加返回類型提示，這樣 `return` 語句必須返回指定類型的值，這有助於提高代碼的可讀性和維護性。

## 一句總結
`return` 關鍵字在 PHP 中用於從函數返回值，並結束函數的執行。