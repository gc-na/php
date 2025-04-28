<!--
Meta Description: # PHP 中的 static 关键字：用法与示例 ## 概述 在 PHP 编程中，`static` 关键字用于声明类属性和方法，使其在类的所有实例中共享，且不需要创建类的实例即可访问。 ## 文档 `static` 关键字的主要目的是提供一种机制，使得类的成员（属性和方法）可以在没有实例化类的情况...
Meta Keywords: static, php, public, function, class
-->

# PHP 中的 static 关键字：用法与示例

## 概述
在 PHP 编程中，`static` 关键字用于声明类属性和方法，使其在类的所有实例中共享，且不需要创建类的实例即可访问。

## 文档
`static` 关键字的主要目的是提供一种机制，使得类的成员（属性和方法）可以在没有实例化类的情况下被访问。它让我们能够创建与类相关联而非与特定对象实例相关联的成员。

### 用途
1. **静态属性**：在类中定义的静态属性会被所有对象共享。
2. **静态方法**：静态方法可以直接通过类名调用，不需要实例化对象。
3. **延迟静态绑定**：PHP 5.3 引入的特性，允许通过 `static` 关键字来调用静态方法或属性，而不依赖于当前对象的类型。

### 使用方式
- 声明静态属性和方法：使用 `static` 关键字。
- 访问静态成员：使用 `::` 操作符。

## 示例
### 静态属性示例
```php
class Counter {
    public static $count = 0;

    public static function increment() {
        self::$count++;
    }
}

Counter::increment();
Counter::increment();
echo Counter::$count; // 输出 2
```

### 静态方法示例
```php
class Math {
    public static function add($a, $b) {
        return $a + $b;
    }
}

echo Math::add(5, 10); // 输出 15
```

### 延迟静态绑定示例
```php
class A {
    public static function who() {
        echo "A";
    }
}

class B extends A {
    public static function who() {
        echo "B";
    }

    public static function test() {
        static::who(); // 使用延迟静态绑定
    }
}

B::test(); // 输出 B
```

## 解释
使用 `static` 关键字时，开发人员应该注意以下几点：
1. **共享状态**：静态属性在所有实例中共享，这可能导致意外的状态变化。
2. **无法访问非静态成员**：静态方法无法访问非静态属性和方法，因为它们没有上下文的对象实例。
3. **延迟静态绑定**：了解延迟静态绑定的行为是关键，它与使用 `self` 关键字的行为不同。

## 一句话总结
在 PHP 中，`static` 关键字允许类属性和方法在没有对象实例的情况下被共享和访问。