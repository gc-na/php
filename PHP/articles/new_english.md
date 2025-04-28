<!--
Meta Description: # Understanding the "new" Keyword in PHP: Instantiating Objects ## Synopsis The `new` keyword in PHP is used to create instances of classes, allowing ...
Meta Keywords: new, class, php, object, keyword
-->

# Understanding the "new" Keyword in PHP: Instantiating Objects

## Synopsis
The `new` keyword in PHP is used to create instances of classes, allowing developers to instantiate objects and leverage object-oriented programming (OOP) principles.

## Documentation

### Purpose
The `new` keyword is fundamental to object-oriented programming in PHP. It enables the instantiation of classes, allowing developers to create objects that encapsulate data and behavior.

### Usage
To use the `new` keyword, simply follow the syntax:

```php
$object = new ClassName();
```

Where `ClassName` is the name of the class you wish to instantiate. You can also pass parameters to the class constructor if it requires them.

### Details
- **Constructor Invocation**: When an object is instantiated using `new`, the class constructor (if defined) is automatically called.
- **Memory Management**: PHP handles memory allocation for objects created with `new`, and developers do not need to manage memory manually.
- **Object Properties and Methods**: Once an object is created, you can access its properties and methods using the `->` operator.

## Examples

### Basic Example
```php
class Car {
    public $color;

    public function __construct($color) {
        $this->color = $color;
    }

    public function getColor() {
        return $this->color;
    }
}

// Creating an instance of the Car class
$myCar = new Car("red");
echo $myCar->getColor(); // Outputs: red
```

### Example with Multiple Instances
```php
class Dog {
    public $name;

    public function __construct($name) {
        $this->name = $name;
    }
}

$dog1 = new Dog("Buddy");
$dog2 = new Dog("Max");

echo $dog1->name; // Outputs: Buddy
echo $dog2->name; // Outputs: Max
```

## Explanation
When using the `new` keyword, keep in mind the following common pitfalls and notes:

- **Undefined Class**: If you attempt to instantiate a class that has not been defined, PHP will throw a fatal error.
- **Constructor Parameters**: Ensure the correct number and type of parameters are passed to the constructor if it requires them.
- **Inheritance and Parent Classes**: If a class extends a parent class, using `new` on the child class will also invoke the parent class constructor if it exists, unless explicitly prevented with `parent::__construct()`.
- **Static Context**: The `new` keyword cannot be used inside static methods to instantiate an object of the class.

## One Line Summary
The `new` keyword in PHP is essential for creating objects from classes, enabling the use of object-oriented programming features.