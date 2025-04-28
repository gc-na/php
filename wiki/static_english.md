<!--
Meta Description: # Understanding 'static' in PHP: A Comprehensive Guide ## Synopsis The `static` keyword in PHP is a powerful feature used to define properties and met...
Meta Keywords: static, class, php, method, methods
-->

# Understanding 'static' in PHP: A Comprehensive Guide

## Synopsis
The `static` keyword in PHP is a powerful feature used to define properties and methods that belong to a class rather than instances of that class, allowing for shared state and behavior across all instances.

## Documentation
The `static` keyword serves multiple purposes in PHP:

1. **Static Properties**: When a property is declared as `static`, it is shared among all instances of the class. This means that it is not tied to any particular object instance but to the class itself.

2. **Static Methods**: Similar to static properties, static methods can be called without creating an instance of the class. They can only access static properties or methods within the class.

3. **Late Static Binding**: Introduced in PHP 5.3, late static binding enables the use of `static` to refer to the called class in a context where the class is inherited. This allows for better flexibility in inheritance scenarios.

### Usage
To declare a static property or method in a class, use the `static` keyword as shown:

```php
class MyClass {
    public static $staticProperty = 'I am static!';

    public static function staticMethod() {
        return 'Called a static method.';
    }
}
```

You can access static members using the scope resolution operator `::`:

```php
echo MyClass::$staticProperty; // Outputs: I am static!
echo MyClass::staticMethod();   // Outputs: Called a static method.
```

### Late Static Binding Example
Late static binding can be utilized using the `static` keyword in conjunction with inheritance:

```php
class ParentClass {
    public static function getClassName() {
        return static::class; // Returns the name of the class that called the method
    }
}

class ChildClass extends ParentClass {}

echo ChildClass::getClassName(); // Outputs: ChildClass
```

## Examples

### Example 1: Static Property
```php
class Counter {
    public static $count = 0;

    public static function increment() {
        self::$count++;
    }
}

Counter::increment();
Counter::increment();
echo Counter::$count; // Outputs: 2
```

### Example 2: Static Method
```php
class Math {
    public static function square($number) {
        return $number * $number;
    }
}

echo Math::square(4); // Outputs: 16
```

### Example 3: Late Static Binding
```php
class Animal {
    public static function identify() {
        return static::class;
    }
}

class Dog extends Animal {}

echo Dog::identify(); // Outputs: Dog
```

## Explanation
While using the `static` keyword provides many advantages, there are some common pitfalls:

- **Accessing Non-static Members**: Static methods cannot access non-static properties directly. Attempting to do so will result in a fatal error.
  
- **Inheritance and Static Methods**: Be cautious with static method overriding. If a child class overrides a static method of the parent class, calling the method on the parent class will still refer to the parent class method unless late static binding is used.

- **Static Context Limitations**: Static methods cannot use `$this` as they do not belong to an instance. This can lead to confusion if not clearly understood.

## One Line Summary
The `static` keyword in PHP allows the definition of properties and methods that belong to a class rather than specific instances, enabling shared functionality and state across all instances.