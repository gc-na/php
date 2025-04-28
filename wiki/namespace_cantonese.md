<!--
Meta Description: # PHP 命名空間 (Namespace) 的詳細指南 ## 概要 命名空間是 PHP 中一個重要的特性，用於組織代碼，避免命名衝突，特別是在大型應用程式或庫中。 ## 文檔 ### 目的 命名空間允許開發者將代碼分組，從而讓不同的代碼片段可以使用相同的類名而不會發生衝突。這對於庫或框架的開發尤為...
Meta Keywords: php, myapp, namespace, product, usercontroller
-->

# PHP 命名空間 (Namespace) 的詳細指南

## 概要
命名空間是 PHP 中一個重要的特性，用於組織代碼，避免命名衝突，特別是在大型應用程式或庫中。

## 文檔
### 目的
命名空間允許開發者將代碼分組，從而讓不同的代碼片段可以使用相同的類名而不會發生衝突。這對於庫或框架的開發尤為重要。

### 使用
在 PHP 中，命名空間使用 `namespace` 關鍵字進行定義。命名空間可以在文件的最上方定義，並且可以包含多層級的命名空間。

#### 定義命名空間
```php
namespace MyApp\Controllers;

class UserController {
    // 類的內容
}
```

#### 使用命名空間
要使用其他命名空間中的類，可以使用 `use` 關鍵字來導入。

```php
namespace MyApp;

use MyApp\Controllers\UserController;

$userController = new UserController();
```

## 範例
以下是一些基本的命名空間使用範例：

### 單一命名空間
```php
namespace MyApp;

class Example {
    public function greet() {
        return "Hello from MyApp!";
    }
}
```

### 多層命名空間
```php
namespace MyApp\Models;

class Product {
    public function info() {
        return "This is a product model.";
    }
}
```

### 使用其他命名空間
```php
namespace MyApp;

use MyApp\Models\Product;

$product = new Product();
echo $product->info();
```

## 解釋
### 常見陷阱
1. **命名衝突**：如果不使用命名空間，可能會與其他類發生名稱衝突，特別是在使用第三方庫時。
2. **命名空間的結構**：命名空間的層級應該清晰且有意義，避免過於複雜的結構。
3. **自動加載**：使用命名空間時，請確保自動加載機制（如 Composer）正確配置，以便能夠正確找到所需的類。

### 附加說明
命名空間不僅限於類，還可以用於函數和常量，這樣可以進一步避免命名衝突。

## 一句總結
PHP 的命名空間是一種組織代碼的方式，能有效避免命名衝突，特別在大型應用中至關重要。