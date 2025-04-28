<!--
Meta Description: # PHP 中的 "protected" 訪問修飾符 ## 簡介 在 PHP 中，"protected" 是一種訪問修飾符，用於控制屬性和方法的可見性。它允許子類別訪問父類中的屬性和方法，但不允許在類的外部直接訪問。這種機制提供了更高的封裝性和數據保護。 ## 文檔 ### 目的 "protecte...
Meta Keywords: protected, name, php, function, class
-->

# PHP 中的 "protected" 訪問修飾符

## 簡介
在 PHP 中，"protected" 是一種訪問修飾符，用於控制屬性和方法的可見性。它允許子類別訪問父類中的屬性和方法，但不允許在類的外部直接訪問。這種機制提供了更高的封裝性和數據保護。

## 文檔
### 目的
"protected" 修飾符主要用於物件導向編程中，以限制對類屬性和方法的訪問，從而保護類的內部狀態。這意味著只有該類及其子類可以訪問被聲明為 "protected" 的成員。

### 用法
在 PHP 中，"protected" 可以用於屬性和方法的聲明。其基本語法如下：

```php
class ParentClass {
    protected $property;

    protected function method() {
        // 方法實現
    }
}

class ChildClass extends ParentClass {
    public function accessParent() {
        $this->property = '可以訪問';
        $this->method();
    }
}

$child = new ChildClass();
// $child->property; // 會報錯，因為外部不能直接訪問 protected 屬性
// $child->method(); // 會報錯，因為外部不能直接訪問 protected 方法
```

## 範例
以下是一個簡單的範例，展示如何使用 "protected" 訪問修飾符：

```php
class Animal {
    protected $name;

    protected function setName($name) {
        $this->name = $name;
    }
}

class Dog extends Animal {
    public function __construct($name) {
        $this->setName($name);
    }

    public function getName() {
        return $this->name; // 這裡會報錯，因為 $name 是 protected
    }
}

$dog = new Dog('Buddy');
// echo $dog->getName(); // 會報錯，因為無法訪問 protected 屬性
```

## 解釋
使用 "protected" 訪問修飾符時需要注意以下幾點：

1. **無法在類外部訪問**：任何嘗試在類外部直接訪問 protected 屬性或方法的行為都會導致錯誤。
2. **子類訪問權限**：子類對父類中定義的 protected 成員具有訪問權限，但如果子類實例化於外部，則無法訪問父類的 protected 成員。
3. **避免冗餘代碼**：使用 protected 可以幫助減少冗餘代碼，因為子類可以直接使用父類的邏輯，這樣可以減少重複代碼的需要。

## 一句總結
"protected" 在 PHP 中是一種訪問修飾符，用於限制屬性和方法的可見性，僅允許其子類訪問。