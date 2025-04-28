<!--
Meta Description: # PHP 命名空間 (Namespace) 的詳細介紹 ## 概述 PHP 的命名空間是一項重要的語言功能，旨在解決全域名稱衝突問題並組織代碼，使其更具可讀性和可維護性。透過命名空間，開發者可以將類別、函數和常量分組，從而避免名稱衝突，特別是在大型應用程式或使用第三方函式庫時。 ## 文檔 ###...
Meta Keywords: php, book, user, namespace, title
-->

# PHP 命名空間 (Namespace) 的詳細介紹

## 概述
PHP 的命名空間是一項重要的語言功能，旨在解決全域名稱衝突問題並組織代碼，使其更具可讀性和可維護性。透過命名空間，開發者可以將類別、函數和常量分組，從而避免名稱衝突，特別是在大型應用程式或使用第三方函式庫時。

## 文檔
### 目的
命名空間的主要目的是為了將代碼片段分隔開來，避免全域範圍中的名稱衝突。這一特性在使用多個庫或框架時尤為重要，因為不同的庫可能會有相同名稱的類別或函數。

### 用法
在 PHP 中，命名空間的定義使用 `namespace` 關鍵字。命名空間可以位於 PHP 檔案的頂部，並可以包含子命名空間。使用命名空間的類別和函數需要使用全名（包括命名空間）來調用。

#### 定義命名空間
```php
namespace MyApp;

class User {
    public function greet() {
        return "Hello, User!";
    }
}
```

#### 使用命名空間
在另一個檔案中使用命名空間的類別時，可以這樣調用：
```php
require 'User.php';

$user = new \MyApp\User();
echo $user->greet(); // 輸出: Hello, User!
```

## 範例
### 基本用法
以下是使用命名空間的基本範例：

```php
// 定義命名空間
namespace MyLibrary;

class Book {
    public function title() {
        return "PHP Programming";
    }
}

// 使用命名空間
namespace AnotherLibrary;

class Book {
    public function title() {
        return "Java Programming";
    }
}

// 引入和使用命名空間
require 'MyLibrary/Book.php';
require 'AnotherLibrary/Book.php';

$phpBook = new \MyLibrary\Book();
$javaBook = new \AnotherLibrary\Book();

echo $phpBook->title(); // 輸出: PHP Programming
echo $javaBook->title(); // 輸出: Java Programming
```

### 引入命名空間
在使用命名空間時，PHP 允許使用 `use` 關鍵字來引入其他命名空間的類別，這樣可以避免每次都寫出全名。

```php
namespace MyApplication;

use MyLibrary\Book as LibraryBook;

$book = new LibraryBook();
echo $book->title(); // 輸出: PHP Programming
```

## 解釋
### 常見問題
- **未找到類別錯誤**：在使用命名空間時，如果不正確引用類別的全名，會導致 `Class not found` 的錯誤。
- **全域範圍衝突**：如果在同一檔案中同時使用相同名稱的類別，則需要使用 `use` 來明確指定要使用的類別。
- **命名空間的層次結構**：命名空間可以使用斜杠 `/` 來表示層次結構，但在不同的檔案中使用時，必須保持一致。

## 總結
PHP 的命名空間功能極大地增強了代碼的組織性，幫助開發者避免名稱衝突，促進了代碼的可讀性和可維護性。