<!--
Meta Description: # PHP 介面 (Interface) 的詳細解說與用法 ## 簡介 在 PHP 中，介面（Interface）是一種定義類別必須實現的合約，允許不同的類別在不共享相同父類的情況下實現相同的功能。介面提供了一種強制實現特定方法的方式，使得代碼更加一致和可維護。 ## 文檔 介面在 PHP 中的主要...
Meta Keywords: public, function, area, php, circle
-->

# PHP 介面 (Interface) 的詳細解說與用法

## 簡介
在 PHP 中，介面（Interface）是一種定義類別必須實現的合約，允許不同的類別在不共享相同父類的情況下實現相同的功能。介面提供了一種強制實現特定方法的方式，使得代碼更加一致和可維護。

## 文檔
介面在 PHP 中的主要目的是定義一組方法，這些方法必須被實現的類別所實現。介面只能包含方法的聲明，而不包含方法的實現。介面可以被多個類別實現，這樣可以達到多重繼承的效果。

### 使用方式
定義介面的語法如下：
```php
interface InterfaceName {
    public function methodName();
}
```

任何實現這個介面的類別都需要提供這些方法的具體實現。例如：
```php
interface Animal {
    public function makeSound();
}

class Dog implements Animal {
    public function makeSound() {
        return "Woof!";
    }
}

class Cat implements Animal {
    public function makeSound() {
        return "Meow!";
    }
}
```

在這個例子中，`Animal` 介面定義了一個名為 `makeSound` 的方法，`Dog` 和 `Cat` 類別實現了這個介面，並提供了各自的方法實現。

## 範例
以下是更詳細的範例，展示如何使用介面來實現多個類別：
```php
interface Shape {
    public function area();
}

class Circle implements Shape {
    private $radius;

    public function __construct($radius) {
        $this->radius = $radius;
    }

    public function area() {
        return pi() * ($this->radius ** 2);
    }
}

class Rectangle implements Shape {
    private $width;
    private $height;

    public function __construct($width, $height) {
        $this->width = $width;
        $this->height = $height;
    }

    public function area() {
        return $this->width * $this->height;
    }
}

$circle = new Circle(5);
echo "Circle area: " . $circle->area(); // Circle area: 78.539816339744

$rectangle = new Rectangle(4, 6);
echo "Rectangle area: " . $rectangle->area(); // Rectangle area: 24
```

在此範例中，`Shape` 介面要求實現其的類別提供計算面積的方法，`Circle` 和 `Rectangle` 分別提供了自己的實現。

## 解釋
使用介面時，開發者需注意以下幾點：
1. **方法簽名一致性**：所有實現介面的類別必須保持方法簽名（名稱和參數）一致，否則將導致錯誤。
2. **多重繼承**：PHP 不支持多重繼承，但通過介面可以實現類似的功能。類別可以實現多個介面。
3. **屬性限制**：介面不能包含屬性，只能定義方法，因此需要透過類別來儲存數據。
4. **無法實例化**：介面本身不能被實例化，只能被類別實現。

## 總結
介面是 PHP 中一個強大的功能，提供了一種靈活的方式來實現多重繼承和加強代碼的一致性。通過正確使用介面，可以使代碼更具可讀性和可維護性。