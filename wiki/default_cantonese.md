<!--
Meta Description: # PHP 的 "default" 關鍵字詳解 ## 概要 在 PHP 中，"default" 是一個關鍵字，主要用於 switch 語句中，作為預設情況的處理選項。當沒有匹配的 case 時，default 區塊中的代碼將會被執行。 ## 文檔 "Default" 關鍵字的主要目的是提供一個回退選...
Meta Keywords: case, default, break, switch, php
-->

# PHP 的 "default" 關鍵字詳解

## 概要
在 PHP 中，"default" 是一個關鍵字，主要用於 switch 語句中，作為預設情況的處理選項。當沒有匹配的 case 時，default 區塊中的代碼將會被執行。

## 文檔
"Default" 關鍵字的主要目的是提供一個回退選項，以便在 switch 語句中處理所有未明確列出的選項。這對於需要處理多種情況的情境非常有用，特別是當某些情況不在預期之內時。

### 用法
在使用 switch 語句時，"default" 應放在所有 case 的最後。其語法如下：

```php
switch (表達式) {
    case 值1:
        // 當表達式為 值1 時執行的代碼
        break;
    case 值2:
        // 當表達式為 值2 時執行的代碼
        break;
    default:
        // 當沒有匹配的情況時執行的代碼
        break;
}
```

### 詳細說明
- **表達式**：這是要檢查的變量或值。
- **case**：每個 case 都是一個可能的匹配值。如果表達式與某個 case 匹配，則執行該 case 中的代碼。
- **break**：用於結束 switch 語句的執行。如果沒有 break，PHP 將會繼續執行後續的 case（這稱為「穿透」）。
- **default**：在所有 case 都不匹配時執行的代碼塊。這是可選的，但建議包含，以處理意料之外的情況。

## 示例
以下是如何使用 default 的基本示例：

```php
$day = 5;

switch ($day) {
    case 1:
        echo "星期一";
        break;
    case 2:
        echo "星期二";
        break;
    case 3:
        echo "星期三";
        break;
    case 4:
        echo "星期四";
        break;
    case 5:
        echo "星期五";
        break;
    default:
        echo "無效的日期";
        break;
}
```

在這個例子中，由於 $day 的值是 5，輸出將會是 "星期五"。

## 解釋
常見的陷阱或注意事項包括：
- 忘記在 case 區塊後添加 break，可能導致意外執行後續的 case。
- default 區塊是可選的，但建議在可能的情況下使用，以提高代碼的健壯性。
- 如果 switch 語句的表達式未匹配任何 case，default 區塊將會被執行，這有助於處理錯誤或未預見的情況。

## 一行總結
在 PHP 中，"default" 關鍵字用於 switch 語句中，作為處理所有未匹配情況的預設選項。