<!--
Meta Description: # PHP 類別 (Class) 的詳細說明與用法 ## 簡介 在 PHP 中，類別 (Class) 是物件導向程式設計的核心概念之一。它允許開發者創建自定義資料型別，並整合屬性和方法以實現更靈活和可擴展的程式碼結構。 ## 文檔 ### 目的 類別提供了一種將相關的屬性和行為封裝在一起的方式，這樣...
Meta Keywords: php, public, class, name, dog
-->

# PHP 類別 (Class) 的詳細說明與用法

## 簡介
在 PHP 中，類別 (Class) 是物件導向程式設計的核心概念之一。它允許開發者創建自定義資料型別，並整合屬性和方法以實現更靈活和可擴展的程式碼結構。

## 文檔
### 目的
類別提供了一種將相關的屬性和行為封裝在一起的方式，這樣可以創建物件的實例以執行特定的任務。透過類別，開發者可以實現繼承、封裝和多型等物件導向的特性。

### 用法
在 PHP 中，類別是使用 `class` 關鍵字來定義的。以下是類別的基本結構：

```php
class ClassName {
    // 屬性
    public $property;

    // 建構函數
    public function __construct($value) {
        $this->property = $value;
    }

    // 方法
    public function method() {
        return "屬性值: " . $this->property;
    }
}
```

### 詳細說明
- **屬性**：類別中的變數，用於儲存物件的狀態。
- **方法**：類別中的函數，定義物件的行為。
- **建構函數**：特殊的方法，當物件被創建時自動呼叫，用於初始化屬性。
- **繼承**：可以讓一個類別擴展另一個類別，以重用和擴展功能。

## 範例
以下是類別的基本用法範例：

### 定義與實例化類別
```php
class Animal {
    public $name;

    public function __construct($name) {
        $this->name = $name;
    }

    public function speak() {
        return $this->name . " 會叫.";
    }
}

// 創建物件實例
$dog = new Animal("狗");
echo $dog->speak(); // 輸出: 狗 會叫.
```

### 繼承範例
```php
class Dog extends Animal {
    public function speak() {
        return $this->name . " 汪汪叫.";
    }
}

$dog = new Dog("小狗");
echo $dog->speak(); // 輸出: 小狗 汪汪叫.
```

## 解釋
- **常見陷阱**：初學者常常忽略 `public`、`private` 和 `protected` 的可見性修飾符。這會影響屬性和方法的存取權限。
- **物件的複製**：使用 `clone` 關鍵字來複製物件時，需注意深層複製和淺層複製的差異。
- **建構函數**：如果未定義建構函數，PHP 會提供一個預設的空建構函數。

## 一句總結
PHP 的類別 (Class) 是物件導向程式設計的基石，允許開發者創建自定義資料型別來加強程式碼的結構與可維護性。