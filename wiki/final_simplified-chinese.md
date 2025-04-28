<!--
Meta Description: # PHP中的final关键字：用法与示例 ## 摘要 在PHP中，`final`关键字用于限制类的继承和方法的重写，从而确保代码的安全性和可预测性。 ## 文档 `final`关键字可以应用于类和方法。它的主要目的是防止某个类被继承或者某个方法被重写。使用`final`的类或方法可以提高代码的稳定...
Meta Keywords: final, class, function, public, php
-->

# PHP中的final关键字：用法与示例

## 摘要
在PHP中，`final`关键字用于限制类的继承和方法的重写，从而确保代码的安全性和可预测性。

## 文档
`final`关键字可以应用于类和方法。它的主要目的是防止某个类被继承或者某个方法被重写。使用`final`的类或方法可以提高代码的稳定性和可维护性。

### 用法
1. **final类**：声明为`final`的类不能被其他类继承。
   ```php
   final class BaseClass {
       // 类的内容
   }

   class ChildClass extends BaseClass { // 这将导致错误
   }
   ```

2. **final方法**：声明为`final`的方法不能在子类中被重写。
   ```php
   class BaseClass {
       final public function display() {
           echo "This is a final method.";
       }
   }

   class ChildClass extends BaseClass {
       public function display() { // 这将导致错误
           echo "Trying to override.";
       }
   }
   ```

## 示例
以下是`final`关键字在PHP中的一些基本用法示例：

### 示例1：final类
```php
final class Singleton {
    private static $instance;

    private function __construct() {}

    public static function getInstance() {
        if (self::$instance === null) {
            self::$instance = new Singleton();
        }
        return self::$instance;
    }
}

// 尝试继承将导致错误
// class AnotherClass extends Singleton {}
```

### 示例2：final方法
```php
class ParentClass {
    final public function show() {
        echo "Final method.";
    }
}

class ChildClass extends ParentClass {
    // public function show() { // 这将导致错误
    //     echo "Overriding final method.";
    // }
}
```

## 说明
- **常见问题**：使用`final`类和方法时，开发者需要注意，试图继承final类或重写final方法会导致致命错误。
- **性能考虑**：虽然在一般情况下`final`不会显著影响性能，但它可以帮助PHP在编译期间进行优化，因为它知道这些类和方法不会被修改。
- **设计模式**：在某些设计模式（如单例模式）中，`final`关键字是非常有用的，可以确保类的唯一性和不变性。

## 一句话总结
在PHP中，`final`关键字用于防止类被继承和方法被重写，从而增强代码的安全性和稳定性。