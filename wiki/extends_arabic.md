<!--
Meta Description: # استخدام الكلمة المحجوزة "extends" في PHP: دليل شامل ## الملخص تعتبر الكلمة المحجوزة "extends" في PHP أداة رئيسية في البرمجة الكائنية، حيث تُستخدم لت...
Meta Keywords: extends, php, public, الخصائص, فئة
-->

# استخدام الكلمة المحجوزة "extends" في PHP: دليل شامل

## الملخص
تعتبر الكلمة المحجوزة "extends" في PHP أداة رئيسية في البرمجة الكائنية، حيث تُستخدم لتوسيع الفئات (classes) وتهيئة العلاقات بين الكائنات.

## الوثائق
### الغرض
تُستخدم "extends" لتوريث الخصائص والأساليب من فئة أب إلى فئة فرعية. هذا التوريث يمكن البرمجة من إعادة استخدام الأكواد وتطوير تطبيقات أكثر تعقيدًا بكفاءة.

### الاستخدام
عند تعريف فئة جديدة، يمكن استخدام "extends" للإشارة إلى الفئة التي سيتم وراثتها. على سبيل المثال:

```php
class ParentClass {
    public function sayHello() {
        return "Hello from ParentClass";
    }
}

class ChildClass extends ParentClass {
    public function sayGoodbye() {
        return "Goodbye from ChildClass";
    }
}
```

في المثال أعلاه، `ChildClass` يرث الأسلوب `sayHello()` من `ParentClass`، مما يعني أنه يمكن استخدامه داخل `ChildClass` مباشرة.

### التفاصيل
- **التوريث الأحادي**: PHP تدعم التوريث الأحادي فقط، مما يعني أن كل فئة يمكن أن ترث من فئة واحدة فقط.
- **الوصول إلى الخصائص والأساليب**: يمكن للفئة الفرعية الوصول إلى الخصائص العامة (public) والخاصة (protected) من الفئة الأب، ولكن لا يمكنها الوصول إلى الخصائص الخاصة (private).

## الأمثلة
### مثال 1: استخدام الكلمة المحجوزة "extends"
```php
class Animal {
    public function speak() {
        return "Animal sound";
    }
}

class Dog extends Animal {
    public function speak() {
        return "Bark";
    }
}

$dog = new Dog();
echo $dog->speak(); // Outputs: Bark
```

### مثال 2: وراثة الخصائص
```php
class Vehicle {
    protected $wheels = 4;

    public function getWheels() {
        return $this->wheels;
    }
}

class Bike extends Vehicle {
    public function getWheels() {
        return $this->wheels - 2; // Bikes have 2 wheels
    }
}

$bike = new Bike();
echo $bike->getWheels(); // Outputs: 2
```

## الشرح
### العوائق الشائعة
- **التوريث المتعدد**: كما ذكر، PHP لا تدعم التوريث المتعدد، لذا يجب أن تكون حذرًا عند تصميم الفئات.
- **تجاوز الأساليب**: عند تجاوز الأساليب في الفئة الفرعية، يجب استخدام `parent::` لاستدعاء الأسلوب من الفئة الأب إذا لزم الأمر.
  
### ملاحظات إضافية
- تأكد من فهم مستويات الوصول (public, protected, private) وتأثيرها على كيفية الوصول إلى الخصائص والأساليب.
- تعتبر الكلمة المحجوزة "extends" جزءًا أساسيًا من البرمجة الكائنية في PHP، لذا يُنصح بممارستها بشكل مكثف.

## ملخص جملة واحدة
تُستخدم الكلمة المحجوزة "extends" في PHP لتوريث الخصائص والأساليب من فئة أب إلى فئة فرعية، مما يسهل إعادة استخدام الأكواد.