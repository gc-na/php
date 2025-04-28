<!--
Meta Description: # PHP 中的 "protected" 关键字详解 ## 概述 在 PHP 中，"protected" 是一种访问修饰符，用于控制类属性和方法的可见性。它允许子类访问父类的属性和方法，但不允许通过类的实例直接访问。这种特性有助于实现封装，增强代码的安全性和可维护性。 ## 文档 ### 目的 "p...
Meta Keywords: protected, php, species, class, function
-->

# PHP 中的 "protected" 关键字详解

## 概述
在 PHP 中，"protected" 是一种访问修饰符，用于控制类属性和方法的可见性。它允许子类访问父类的属性和方法，但不允许通过类的实例直接访问。这种特性有助于实现封装，增强代码的安全性和可维护性。

## 文档
### 目的
"protected" 修饰符用于定义类的成员（属性和方法）的访问权限。被标记为 "protected" 的成员只能在定义它们的类内部以及所有子类中访问，而无法在类的外部直接访问。

### 使用
在 PHP 中，可以通过以下方式定义 "protected" 成员：

```php
class ParentClass {
    protected $protectedProperty; // 受保护的属性

    protected function protectedMethod() { // 受保护的方法
        // 方法逻辑
    }
}

class ChildClass extends ParentClass {
    public function accessProtected() {
        $this->protectedProperty = "可以访问";
        $this->protectedMethod(); // 可以调用
    }
}

$parent = new ParentClass();
$parent->protectedProperty = "不能访问"; // 错误：无法访问受保护属性
$parent->protectedMethod(); // 错误：无法访问受保护方法
```

### 细节
- **访问限制**：受保护的成员可以在其定义类及其子类中访问，但无法在类的实例化对象中直接访问。
- **构造函数**：受保护的属性可以在构造函数中赋值并初始化。
- **多重继承**：PHP 不支持多重继承，但可以通过接口或 traits 实现类似的功能。

## 示例
以下是使用 "protected" 的基本示例：

```php
class Animal {
    protected $species;

    protected function setSpecies($species) {
        $this->species = $species;
    }
}

class Dog extends Animal {
    public function __construct() {
        $this->setSpecies("犬科");
    }
}

$dog = new Dog();
// $dog->species; // 错误：无法访问受保护属性
```

## 说明
- **常见问题**：初学者常常混淆 "protected" 和 "private" 关键字。与 "private" 不同，"protected" 允许子类访问父类的成员。
- **封装与继承**：使用 "protected" 可以在确保封装性的同时，允许子类对父类的部分功能进行扩展。
- **代码可读性**：合理使用 "protected" 有助于提高代码的可读性和可维护性，但过度使用可能导致代码结构复杂。

## 一句话总结
"protected" 是 PHP 中的一种访问修饰符，允许子类访问父类的成员，但不允许外部直接访问。