<!--
Meta Description: # PHP 的 "return" 語句：用法與示例 ## 概述 在 PHP 編程中，`return` 是一個關鍵字，用於從函數中返回值。這個語句不僅能終止函數的執行，還能將計算結果或狀態傳回調用該函數的地方。 ## 文檔 `return` 語句的主要目的是提供一種機制，讓函數能夠將結果或數據傳遞給它...
Meta Keywords: return, php, function, getnumber, echo
-->

# PHP 的 "return" 語句：用法與示例

## 概述
在 PHP 編程中，`return` 是一個關鍵字，用於從函數中返回值。這個語句不僅能終止函數的執行，還能將計算結果或狀態傳回調用該函數的地方。

## 文檔
`return` 語句的主要目的是提供一種機制，讓函數能夠將結果或數據傳遞給它的調用者。當 PHP 遇到 `return` 語句時，函數會立即停止執行，並返回指定的值。這使得函數可以被重複調用，並根據不同的輸入返回不同的結果。

### 使用方式
- **基本語法**：
  ```php
  return [value];
  ```

- **返回值類型**：
  PHP 的函數可以返回任何類型的數據，包括整數、浮點數、字符串、數組和對象等。

- **示範**：
  ```php
  function add($a, $b) {
      return $a + $b;
  }
  ```

## 示例
以下是 `return` 語句的一些基本使用示例：

### 示例 1：返回整數
```php
function getNumber() {
    return 42;
}

echo getNumber(); // 輸出：42
```

### 示例 2：返回字符串
```php
function greet($name) {
    return "Hello, " . $name;
}

echo greet("World"); // 輸出：Hello, World
```

### 示例 3：返回數組
```php
function getColors() {
    return ["red", "green", "blue"];
}

$colors = getColors();
print_r($colors); // 輸出：Array ( [0] => red [1] => green [2] => blue )
```

## 解釋
在使用 `return` 時，開發者需要注意以下幾點：

1. **多個返回值**：在函數中只能使用一次 `return` 語句，但可以返回一個數組來模擬多個返回值。
   
   ```php
   function getCoordinates() {
       return [10, 20];
   }
   ```

2. **函數執行終止**：一旦 PHP 遇到 `return` 語句，函數的執行將立即終止，後面的代碼將不會被執行。

3. **未返回值的函數**：如果一個函數未使用 `return` 語句，則默認返回 `NULL`。

4. **作用域**：返回的值將在調用該函數的上下文中可用，這意味著返回的數據可以被賦值給變數或直接用於其他計算。

## 一句總結
`return` 是 PHP 中用於從函數返回值的關鍵語句，能夠有效地終止函數執行並將結果傳回調用者。