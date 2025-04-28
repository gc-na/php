<!--
Meta Description: # PHP 的 clone：深度複製物件的技巧 ## 概述 在 PHP 中，`clone` 是用於創建物件的淺層複製的關鍵字。它允許開發者生成一個物件的副本，並保持原物件的屬性與方法，但不會影響到原物件的參考。 ## 文檔 ### 目的 `clone` 關鍵字的主要目的是提供一種方便的方式來複製物件...
Meta Keywords: clone, name, address, public, age
-->

# PHP 的 clone：深度複製物件的技巧

## 概述
在 PHP 中，`clone` 是用於創建物件的淺層複製的關鍵字。它允許開發者生成一個物件的副本，並保持原物件的屬性與方法，但不會影響到原物件的參考。

## 文檔
### 目的
`clone` 關鍵字的主要目的是提供一種方便的方式來複製物件。當您需要創建一個新的物件實例，但又想保留原有物件的狀態時，`clone` 是非常有用的。

### 使用方式
要使用 `clone`，只需在要複製的物件前加上關鍵字 `clone`。以下是基本語法：

```php
$newObject = clone $originalObject;
```

### 詳細說明
當使用 `clone` 時，PHP 會創建一個新的物件實例。這個新實例的屬性值會與原始物件的屬性值相同。然而，對於物件屬性，`clone` 是淺層複製，這意味著如果屬性是物件，則新物件的屬性將指向原始物件的相同實例。若要實現深度複製，您需要在物件類中定義 `__clone()` 方法。

## 範例
以下是使用 `clone` 的基本範例：

```php
class Person {
    public $name;
    public $age;

    public function __construct($name, $age) {
        $this->name = $name;
        $this->age = $age;
    }
}

$originalPerson = new Person("John", 30);
$clonedPerson = clone $originalPerson;

echo $originalPerson->name; // 輸出 John
echo $clonedPerson->name;    // 輸出 John

$clonedPerson->name = "Jane"; // 修改克隆物件的名稱

echo $originalPerson->name; // 輸出 John
echo $clonedPerson->name;    // 輸出 Jane
```

## 解釋
在使用 `clone` 時，開發者可能會遇到以下問題：
- **淺層複製**：如果物件屬性是物件，那麼 `clone` 只會複製它的引用，這可能導致在一個物件中的改變影響到另一個物件。
- **自定義 `__clone()` 方法**：對於需要深度複製的物件，開發者應該實現類中的 `__clone()` 方法，並在該方法中手動複製引用的屬性。

```php
class Address {
    public $city;

    public function __construct($city) {
        $this->city = $city;
    }
}

class Person {
    public $name;
    public $age;
    public $address;

    public function __construct($name, $age, Address $address) {
        $this->name = $name;
        $this->age = $age;
        $this->address = $address;
    }

    public function __clone() {
        $this->address = clone $this->address; // 深度複製
    }
}

$originalAddress = new Address("Taipei");
$originalPerson = new Person("John", 30, $originalAddress);
$clonedPerson = clone $originalPerson;

$clonedPerson->address->city = "Kaohsiung"; // 修改克隆物件的地址

echo $originalPerson->address->city; // 輸出 Taipei
echo $clonedPerson->address->city;    // 輸出 Kaohsiung
```

## 一句話總結
在 PHP 中，`clone` 是用於創建物件淺層複製的關鍵字，並可透過定義 `__clone()` 方法實現深度複製。