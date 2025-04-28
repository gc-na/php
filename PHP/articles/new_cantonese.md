<!--
Meta Description: # PHP 中的 "new" 關鍵字：用於創建對象的功能 ## 簡介 在 PHP 中，`new` 關鍵字是用來創建對象的主要工具。它允許開發者根據類定義實例化對象，並可用於調用類中的方法和屬性。 ## 文檔 `new` 關鍵字的主要目的是創建一個類的實例。在面向對象編程中，類是對象的模板，而 `ne...
Meta Keywords: new, php, public, color, user
-->

# PHP 中的 "new" 關鍵字：用於創建對象的功能

## 簡介
在 PHP 中，`new` 關鍵字是用來創建對象的主要工具。它允許開發者根據類定義實例化對象，並可用於調用類中的方法和屬性。

## 文檔
`new` 關鍵字的主要目的是創建一個類的實例。在面向對象編程中，類是對象的模板，而 `new` 則是實際創建對象的指令。

### 使用方法：
1. **定義類**：首先需要定義一個類。
2. **使用 `new` 創建對象**：使用 `new` 關鍵字來實例化該類。

### 詳細說明：
- 當使用 `new` 創建對象時，PHP 會自動調用該類的構造函數（`__construct()`），如果存在的話。
- 新創建的對象會被賦予一個變量，用來進行後續操作。
- 可以在創建對象時傳遞參數給構造函數。

## 範例
### 基本使用範例：
```php
<?php
class Car {
    public $color;
    
    public function __construct($color) {
        $this->color = $color;
    }
    
    public function getColor() {
        return $this->color;
    }
}

// 使用 new 創建一個 Car 對象
$myCar = new Car("紅色");
echo $myCar->getColor(); // 輸出：紅色
?>
```

### 傳遞參數範例：
```php
<?php
class User {
    public $name;
    
    public function __construct($name) {
        $this->name = $name;
    }
}

// 創建 User 對象並傳遞參數
$user = new User("小明");
echo $user->name; // 輸出：小明
?>
```

## 解釋
- **公共屬性和方法**：使用 `new` 創建對象後，可以直接訪問該對象的公共屬性和方法。
- **私有和保護屬性**：私有屬性和方法不能直接從對象外部訪問，必須通過公共方法來訪問。
- **常見錯誤**：如果類未定義構造函數，使用 `new` 時不會報錯，但對象的屬性將是未定義的。確保類正確定義，並適當處理構造函數的參數。

## 單句總結
`new` 關鍵字在 PHP 中用於創建類的實例，並調用其方法和屬性。