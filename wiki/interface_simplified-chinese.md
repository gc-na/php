<!--
Meta Description: # PHP 接口（Interface）详解与使用示例 ## 摘要 在 PHP 中，接口是一种定义类必须实现的方法的契约。接口提供了一种方法来定义统一的 API，使得不同的类可以实现相同的功能。 ## 文档 ### 目的 接口的主要目的是实现多态性，使得不同的类能够实现相同的方法，并且可以被同一类型的...
Meta Keywords: public, php, function, interface, implements
-->

# PHP 接口（Interface）详解与使用示例

## 摘要
在 PHP 中，接口是一种定义类必须实现的方法的契约。接口提供了一种方法来定义统一的 API，使得不同的类可以实现相同的功能。

## 文档
### 目的
接口的主要目的是实现多态性，使得不同的类能够实现相同的方法，并且可以被同一类型的变量引用。通过使用接口，开发者可以定义一组方法，而不需要关心具体的实现。

### 用法
在 PHP 中，接口使用 `interface` 关键字定义。接口中的方法不能包含任何实现，必须由实现该接口的类来提供。

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

### 细节
- **定义接口**：接口使用 `interface` 关键字定义，接口名称通常以大写字母开头。
- **实现接口**：类使用 `implements` 关键字来实现接口，必须实现接口中定义的所有方法。
- **多重接口**：一个类可以实现多个接口，使用逗号分隔。
- **常量**：接口可以定义常量，所有实现该接口的类都可以访问这些常量。

## 示例
以下是简单的接口用法示例：

```php
interface Vehicle {
    public function start();
}

class Car implements Vehicle {
    public function start() {
        return "Car started.";
    }
}

class Bike implements Vehicle {
    public function start() {
        return "Bike started.";
    }
}

$myCar = new Car();
echo $myCar->start(); // 输出: Car started.

$myBike = new Bike();
echo $myBike->start(); // 输出: Bike started.
```

## 说明
- **常见问题**：实现接口时，方法的访问修饰符必须是 `public`，否则会导致错误。
- **接口不能实例化**：你不能直接创建接口的实例，只能通过实现该接口的类来实例化。
- **继承**：接口可以继承其他接口，允许形成更复杂的接口结构。
- **类型提示**：在方法参数和返回类型中可以使用接口进行类型提示，增强代码的可读性和可维护性。

## 一句话总结
在 PHP 中，接口是一种定义类必须实现的方法的契约，促进了代码的多态性和一致性。