<!--
Meta Description: # 在 PHP 中使用 require_once 的完整指南 ## 概述 `require_once` 是 PHP 中的一個命令，用於包含和執行指定的檔案。與 `require` 相似，`require_once` 確保檔案只被包含一次，避免重複定義函數、類或變數等問題。 ## 文檔 `requir...
Meta Keywords: php, require_once, 檔案路徑, require, config
-->

# 在 PHP 中使用 require_once 的完整指南

## 概述
`require_once` 是 PHP 中的一個命令，用於包含和執行指定的檔案。與 `require` 相似，`require_once` 確保檔案只被包含一次，避免重複定義函數、類或變數等問題。

## 文檔
`require_once` 的主要目的是引入一個檔案，並確保該檔案在同一請求中只被加載一次。這對於大型應用程序中的模組化設計尤其重要。當使用 `require_once` 時，如果檔案已經被包含，PHP 將不會再次加載它，這樣可以提高效能並防止錯誤。

### 語法
```php
require_once '檔案路徑';
```

### 參數
- `檔案路徑`：要包含的檔案的路徑，可以是相對路徑或絕對路徑。

### 返回值
- 如果檔案成功被包含，`require_once` 將返回 `true`，如果檔案無法加載，則會發出致命錯誤並停止執行。

## 範例
以下是使用 `require_once` 的基本範例：

### 範例 1：包含一個檔案
```php
require_once 'config.php';
```
在這個範例中，`config.php` 檔案只會被加載一次。

### 範例 2：防止重複加載
```php
require_once 'functions.php';
// 這裡可以安全地調用 functions.php 中定義的函數
myFunction();
```

### 範例 3：錯誤處理
```php
if (file_exists('non_existent.php')) {
    require_once 'non_existent.php';
} else {
    echo '檔案不存在。';
}
```
在這個範例中，檔案是否存在會先被檢查，避免致命錯誤。

## 解釋
使用 `require_once` 時需注意以下幾點：
- **檔案路徑**：確保提供的檔案路徑正確，否則會導致致命錯誤。
- **性能考量**：由於 `require_once` 會檢查檔案是否已經被包含，這可能比 `require` 稍慢，但通常這種性能差異在大多數應用中是微不足道的。
- **命名空間**：在使用命名空間的情況下，確保檔案中定義的函數或類名不會重複，這樣可以避免命名衝突。

## 一句總結
`require_once` 是 PHP 中一個強大的包含命令，能有效防止檔案重複加載，確保代碼的穩定性與效能。