<!--
Meta Description: # PHP 的 require_once 指令：確保單次包含檔案 ## 概述 `require_once` 是 PHP 中的一個語言結構，用於包含和執行指定的檔案。當需要確保某個檔案僅被包含一次時，`require_once` 是一個理想的選擇，避免重複包含導致的錯誤。 ## 文檔 ### 目的 `...
Meta Keywords: php, require_once, example, 檔案路徑, helloworld
-->

# PHP 的 require_once 指令：確保單次包含檔案

## 概述
`require_once` 是 PHP 中的一個語言結構，用於包含和執行指定的檔案。當需要確保某個檔案僅被包含一次時，`require_once` 是一個理想的選擇，避免重複包含導致的錯誤。

## 文檔
### 目的
`require_once` 的主要目的是在 PHP 腳本中引入外部檔案，如函數庫、類別定義或其他腳本，並確保該檔案在同一請求中不會被重複載入。

### 用法
語法如下：
```php
require_once '檔案路徑';
```
在這裡，`檔案路徑` 是您希望包含的檔案的路徑。如果檔案已經被包含過，`require_once` 不會再次執行該檔案，這有助於避免重複定義或重複執行的問題。

### 詳細說明
- **錯誤處理**：如果指定的檔案無法找到，`require_once` 會產生致命錯誤並終止腳本執行。這與 `include_once` 的行為不同，後者會發出警告但不中止執行。
- **性能考量**：使用 `require_once` 可以提高性能，因為 PHP 會檢查檔案是否已經包含過，避免不必要的檔案讀取和執行。
- **作用範圍**：被包含檔案中的變數和函數將在當前作用域中可用。

## 範例
### 基本用法
以下是一個使用 `require_once` 的簡單範例：

```php
// example.php
function helloWorld() {
    echo "Hello, World!";
}

// main.php
require_once 'example.php';
helloWorld(); // 輸出: Hello, World!
```

### 檔案重複包含示範
```php
// example.php
echo "This will only show once.";

// main.php
require_once 'example.php'; // 第一次包含
require_once 'example.php'; // 第二次包含，將不會執行
```
在這個例子中，`"This will only show once."` 只會被顯示一次。

## 解釋
### 常見陷阱
- **路徑錯誤**：確保提供的檔案路徑正確，否則會導致致命錯誤。
- **循環包含**：如果檔案 A 包含檔案 B，而檔案 B 又包含檔案 A，這會導致循環包含問題。`require_once` 可以防止這種情況，但仍需謹慎設計檔案結構。
- **作用域問題**：被包含的檔案中的變數需小心使用，避免與當前腳本中的變數命名衝突。

## 一句總結
`require_once` 是 PHP 中用於安全地包含檔案的指令，確保檔案僅被載入一次，從而避免重複定義和執行問題。