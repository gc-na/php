<!--
Meta Description: # PHP 中的 "protected" 關鍵字：訪問控制的基礎 ## 概述 在 PHP 中，`protected` 是一種訪問控制修飾符，用於限制對類屬性和方法的訪問。這個修飾符允許子類別訪問父類別中的受保護成員，卻不允許任何外部代碼直接訪問。 ## 文檔 ### 目的 `protected` 關...
Meta Keywords: protected, php, value, function, class
-->

# PHP 中的 "protected" 關鍵字：訪問控制的基礎

## 概述
在 PHP 中，`protected` 是一種訪問控制修飾符，用於限制對類屬性和方法的訪問。這個修飾符允許子類別訪問父類別中的受保護成員，卻不允許任何外部代碼直接訪問。

## 文檔
### 目的
`protected` 關鍵字的主要目的是提供一種訪問控制機制，使得類的內部實現可以被子類別使用，而外部代碼則無法直接訪問這些成員。這樣的設計有助於封裝和數據保護，並促進了對象導向編程的最佳實踐。

### 使用方法
在 PHP 中，`protected` 修飾符可以用於類的屬性和方法。當一個屬性或方法被聲明為 `protected` 時，它只能在該類及其子類中被訪問。

### 詳細說明
- **屬性範例**：
  ```php
  class Animal {
      protected $name;

      public function setName($name) {
          $this->name = $name;
      }
  }
  ```

- **方法範例**：
  ```php
  class Animal {
      protected function makeSound() {
          return "Some sound";
      }
  }

  class Dog extends Animal {
      public function bark() {
          return $this->makeSound();
      }
  }
  ```

在以上例子中，`$name` 和 `makeSound()` 方法都是 `protected`，因此 `Dog` 類可以訪問這些成員，而無法在類外部直接訪問。

## 範例
### 基本使用
```php
class ParentClass {
    protected $value;

    protected function displayValue() {
        return $this->value;
    }
}

class ChildClass extends ParentClass {
    public function setValue($value) {
        $this->value = $value;
    }

    public function getValue() {
        return $this->displayValue();
    }
}

$child = new ChildClass();
$child->setValue(10);
echo $child->getValue(); // 輸出 10
```

### 嘗試直接訪問
```php
$parent = new ParentClass();
// 這行會報錯，因為 $value 是 protected
// echo $parent->value; 
```

## 解釋
- **常見陷阱**：
  - `protected` 成員無法直接通過實例訪問，這是初學者常見的錯誤。
  - 只有當子類實例化時才能訪問 `protected` 成員，這可能會導致意外的訪問問題。

- **注意事項**：
  - `protected` 成員是可繼承的，這意味著子類可以覆蓋父類的 `protected` 方法，這可能會影響到父類的行為。
  - 使用 `protected` 時要謹慎，確保不會無意中暴露敏感數據。

## 一句話總結
在 PHP 中，`protected` 修飾符用於限制類屬性和方法的訪問，使得只有該類及其子類能夠訪問這些成員。