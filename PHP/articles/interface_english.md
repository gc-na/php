<!--
Meta Description: # Understanding Interfaces in PHP: Definition, Usage, and Best Practices ## Synopsis In PHP, an interface is a contract that defines a set of methods ...
Meta Keywords: interface, interfaces, public, methods, class
-->

# Understanding Interfaces in PHP: Definition, Usage, and Best Practices

## Synopsis
In PHP, an interface is a contract that defines a set of methods that a class must implement. This feature provides a way to enforce certain functionalities in classes, promoting a clear structure and enhancing code maintainability.

## Documentation

### Purpose
An interface in PHP allows developers to define a blueprint for classes without providing the implementation. By using interfaces, multiple classes can implement the same set of methods, ensuring that they all adhere to a specific structure. This is particularly useful in object-oriented programming (OOP) for achieving polymorphism and loose coupling.

### Usage
To declare an interface in PHP, the `interface` keyword is used, followed by the interface name. Methods defined in the interface do not have a body; instead, they only list the method signatures. Any class that implements the interface is required to provide concrete implementations for all the methods declared in the interface.

### Details
- **Declaration**: An interface is declared using the `interface` keyword.
- **Implementation**: Classes implement interfaces using the `implements` keyword.
- **Multiple Interfaces**: A class can implement multiple interfaces, allowing for greater flexibility.
- **Access Modifiers**: All methods declared in an interface must be public, as interfaces are intended to expose functionality to other classes.

## Examples

### Basic Interface Declaration and Implementation
```php
// Define an interface
interface Animal {
    public function makeSound();
}

// Implement the interface in a class
class Dog implements Animal {
    public function makeSound() {
        return "Bark";
    }
}

class Cat implements Animal {
    public function makeSound() {
        return "Meow";
    }
}

// Usage
$dog = new Dog();
echo $dog->makeSound(); // Outputs: Bark

$cat = new Cat();
echo $cat->makeSound(); // Outputs: Meow
```

### Multiple Interface Implementation
```php
interface CanFly {
    public function fly();
}

interface CanSwim {
    public function swim();
}

class Duck implements CanFly, CanSwim {
    public function fly() {
        return "Flying high!";
    }

    public function swim() {
        return "Swimming in the lake!";
    }
}

// Usage
$duck = new Duck();
echo $duck->fly();  // Outputs: Flying high!
echo $duck->swim(); // Outputs: Swimming in the lake!
```

## Explanation
While interfaces provide powerful benefits, there are common pitfalls to be aware of:

- **No Method Body**: Remember that interfaces cannot contain method bodies; they only define the method signatures.
- **Inheriting Interfaces**: Interfaces can extend other interfaces, allowing for more complex structures. However, all methods must still be implemented in the implementing class.
- **Not Instantiable**: Interfaces cannot be instantiated directly; they must be implemented by classes.

### Common Gotchas
- **Type Hinting**: When type hinting an interface in method parameters, ensure the implementing classes correctly implement all methods.
- **Method Visibility**: All methods in an interface are inherently public, and attempting to declare them with other visibility modifiers will result in a fatal error.

## One Line Summary
An interface in PHP is a powerful tool for defining a contract that classes must adhere to, enabling polymorphism and promoting code organization.