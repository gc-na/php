<!--
Meta Description: # Understanding the "extends" Keyword in PHP: A Comprehensive Guide ## Synopsis The `extends` keyword in PHP is used to create a class that inherits p...
Meta Keywords: class, parent, extends, php, can
-->

# Understanding the "extends" Keyword in PHP: A Comprehensive Guide

## Synopsis
The `extends` keyword in PHP is used to create a class that inherits properties and methods from another class, enabling code reusability and the establishment of a class hierarchy in object-oriented programming.

## Documentation
### Purpose
The `extends` keyword serves as a fundamental component of PHP’s object-oriented programming (OOP) paradigm. It allows developers to create a new class that inherits characteristics from an existing class, known as the parent or base class. This mechanism promotes code reuse and can simplify maintenance and scalability of applications.

### Usage
To use the `extends` keyword, define a new class and specify the parent class from which it will inherit. The syntax is straightforward:

```php
class ChildClass extends ParentClass {
    // Child class properties and methods
}
```

### Details
- **Single Inheritance**: PHP supports single inheritance, meaning a class can inherit from only one parent class. However, a class can implement multiple interfaces.
- **Access Modifiers**: Properties and methods of the parent class can be public, protected, or private. Only public and protected members are accessible to the child class.
- **Constructor Inheritance**: If the parent class has a constructor, the child class must call it using `parent::__construct()` if necessary.
- **Method Overriding**: A child class can override methods of the parent class to provide specific implementations.

## Examples
### Basic Usage Example

```php
class Animal {
    public function sound() {
        return "Animal sound";
    }
}

class Dog extends Animal {
    public function sound() {
        return "Bark";
    }
}

$dog = new Dog();
echo $dog->sound(); // Outputs: Bark
```

### Constructor Example

```php
class Vehicle {
    protected $type;

    public function __construct($type) {
        $this->type = $type;
    }
}

class Car extends Vehicle {
    private $brand;

    public function __construct($type, $brand) {
        parent::__construct($type);
        $this->brand = $brand;
    }
}

$car = new Car("Sedan", "Toyota");
```

## Explanation
### Common Pitfalls
- **Not Calling Parent Constructor**: Failing to call the parent class constructor in the child class can lead to uninitialized properties, resulting in unexpected behavior.
- **Access Modifiers**: Attempting to access private properties of the parent class directly in the child class will result in a fatal error. Use protected or public access modifiers as needed.
- **Overriding Final Methods**: If a method in the parent class is declared as `final`, it cannot be overridden in the child class, which can lead to confusion if not properly noted.

### Additional Notes
- While PHP does not support multiple inheritance, developers can achieve similar functionality through interfaces.
- The `extends` keyword is essential for implementing polymorphism, where a child class can be treated as an instance of the parent class.

## One Line Summary
The `extends` keyword in PHP facilitates class inheritance, enabling code reuse and the creation of complex class hierarchies in object-oriented programming.