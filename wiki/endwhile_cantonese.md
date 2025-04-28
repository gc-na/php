<!--
Meta Description: # PHP 中的 "endwhile" 指令：結束循環的關鍵字 ## Synopsis "endwhile" 是 PHP 中用於結束 while 循環的語法結構，通常與 "while" 搭配使用，使得在需要使用 HTML 嵌套 PHP 語法時能夠保持代碼的可讀性。 ## Documentation ...
Meta Keywords: endwhile, php, while, count, html
-->

# PHP 中的 "endwhile" 指令：結束循環的關鍵字

## Synopsis
"endwhile" 是 PHP 中用於結束 while 循環的語法結構，通常與 "while" 搭配使用，使得在需要使用 HTML 嵌套 PHP 語法時能夠保持代碼的可讀性。

## Documentation
### 目的
"endwhile" 指令的主要目的是標示 while 循環的結束，提供一種清晰的方式來結束循環的邏輯。它特別適合在需要使用大量 HTML 代碼時，使得 PHP 代碼的結構更簡潔。

### 使用方法
在 PHP 中，"while" 循環通常以如下格式使用：

```php
while (條件) :
    // 執行的代碼
endwhile;
```

這樣的語法提供了一個清晰的結構，使得在循環內部可以輕鬆地嵌入 HTML 代碼。

### 詳細說明
- "while" 循環會在條件為真時持續執行，當條件不再滿足時，循環將結束。
- 使用 "endwhile" 可以取代傳統的 "}" 結束符號，這在某些情況下使得代碼更易於閱讀，特別是當你在循環內包含大量 HTML 內容時。

## Examples
### 基本用法示例
以下是一個簡單的例子，展示了如何使用 "endwhile" 來建立一個基本的 while 循環：

```php
<?php
$count = 1;

while ($count <= 5) :
    echo "計數: " . $count . "<br>";
    $count++;
endwhile;
?>
```

### 嵌套 HTML 的用法示例
當需要在循環內嵌入 HTML 時，"endwhile" 的使用可以顯著提高可讀性：

```php
<?php
$items = ["蘋果", "香蕉", "橙"];
$count = 0;

while ($count < count($items)) : ?>
    <p>水果: <?php echo $items[$count]; ?></p>
<?php 
    $count++;
endwhile; 
?>
```

## Explanation
### 常見陷阱
- 確保在使用 "endwhile" 前有正確的 "while" 開始語句，否則會導致語法錯誤。
- 在 "endwhile" 之前必須使用 ":" 來開始循環的代碼區塊，這是與大括號風格的 while 循環的主要區別。

### 附加說明
- "endwhile" 只用於 while 循環，不能用於其他循環結構（如 for 或 foreach）。
- 使用 "endwhile" 時，代碼的可讀性會有所提升，特別是在與 HTML 結合使用時。

## One Line Summary
"endwhile" 是 PHP 中用來結束 while 循環的語法，提供了清晰的代碼結構，特別適合於嵌入 HTML 的情況。