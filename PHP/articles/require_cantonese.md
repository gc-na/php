<!--
Meta Description: # PHP "require" 語句：用法及最佳實踐 ## 概述 `require` 是 PHP 中的一個語句，用於將指定的檔案內容包含進當前檔案中，並且在檔案缺失或無法加載時會導致致命錯誤。 ## 文檔 ### 目的 `require` 的主要用途是將其他 PHP 檔案的內容引入到當前檔案中。這對...
Meta Keywords: php, require, 檔案路徑, config, databasehost
-->

# PHP "require" 語句：用法及最佳實踐

## 概述
`require` 是 PHP 中的一個語句，用於將指定的檔案內容包含進當前檔案中，並且在檔案缺失或無法加載時會導致致命錯誤。

## 文檔
### 目的
`require` 的主要用途是將其他 PHP 檔案的內容引入到當前檔案中。這對於重用程式碼和分隔功能特別有用。

### 使用方法
基本語法如下：
```php
require '檔案路徑';
```
- **檔案路徑**：指定要包含的檔案路徑，可以是絕對路徑或相對路徑。

### 詳細說明
- 當使用 `require` 引入檔案時，PHP 會立即執行該檔案中的代碼。
- 如果檔案無法找到，PHP 會產生一個致命錯誤並停止執行後續的代碼。
- `require` 常用於引入配置檔案、函數庫或類別定義，以便在多個檔案中共享相同的功能。

## 範例
以下是 `require` 的基本用法示例：

### 範例 1：引入配置檔案
```php
// config.php
$databaseHost = 'localhost';
$databaseUser = 'root';
$databasePass = 'password';

// main.php
require 'config.php';
echo $databaseHost; // 輸出：localhost
```

### 範例 2：引入函數庫
```php
// functions.php
function greet($name) {
    return "Hello, " . $name;
}

// main.php
require 'functions.php';
echo greet('Alice'); // 輸出：Hello, Alice
```

## 解釋
- 使用 `require` 時要確保指定的檔案存在。若檔案不存在，將會導致致命錯誤。
- 如果需要在檔案缺失時繼續執行後續代碼，可以考慮使用 `include`，因為 `include` 只會產生警告，而不會停止執行。

## 一句總結
`require` 是 PHP 中用於強制引入檔案的語句，若檔案缺失會導致致命錯誤。