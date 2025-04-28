<!--
Meta Description: # المحمي (protected) في PHP: التحكم في وصول الخصائص والطرق ## الملخص تعتبر الكلمة المحجوزة "protected" في PHP وسيلة للتحكم في الوصول إلى الخصائص والطر...
Meta Keywords: protected, الخصائص, الوصول, function, name
-->

# المحمي (protected) في PHP: التحكم في وصول الخصائص والطرق

## الملخص
تعتبر الكلمة المحجوزة "protected" في PHP وسيلة للتحكم في الوصول إلى الخصائص والطرق داخل الفئات، مما يسمح بمرونة أكبر في تصميم البرمجيات مع الحفاظ على الخصوصية.

## الوثائق
### الغرض
تُستخدم الكلمة المحجوزة "protected" لتحديد مستوى الوصول للخصائص والطرق في الفئات. الخصائص أو الطرق المُعرفة بأنها "protected" يمكن الوصول إليها من داخل الفئة نفسها، وكذلك من الفئات المشتقة (الفئات الفرعية) التي ترث منها.

### الاستخدام
عند تعريف خاصية أو طريقة داخل فئة، يمكنك استخدام "protected" كالتالي:

```php
class ParentClass {
    protected $protectedProperty;

    protected function protectedMethod() {
        // تنفيذ ما
    }
}

class ChildClass extends ParentClass {
    public function accessProtected() {
        $this->protectedProperty = 'قيمة جديدة';
        $this->protectedMethod();
    }
}
```

### التفاصيل
- يمكن للفئات الفرعية الوصول إلى الخصائص والطرق المحمية، بينما لا يمكن للفئات الخارجية الوصول إليها.
- تعتبر "protected" أكثر أمانًا من "public" ولكن أقل من "private" حيث أن "private" لا يمكن الوصول إليها إلا من داخل نفس الفئة فقط.

## الأمثلة
### مثال 1: استخدام الخصائص المحمية
```php
class Animal {
    protected $name;

    public function setName($name) {
        $this->name = $name;
    }

    public function getName() {
        return $this->name;
    }
}

class Dog extends Animal {
    public function bark() {
        return "Woof! My name is " . $this->getName();
    }
}

$dog = new Dog();
$dog->setName("Buddy");
echo $dog->bark(); // Output: Woof! My name is Buddy
```

### مثال 2: استخدام الطرق المحمية
```php
class Vehicle {
    protected function startEngine() {
        return "Engine started";
    }
}

class Car extends Vehicle {
    public function drive() {
        return $this->startEngine() . " and driving";
    }
}

$car = new Car();
echo $car->drive(); // Output: Engine started and driving
```

## الشرح
### الأخطاء الشائعة
- **عدم القدرة على الوصول إلى الخصائص المحمية من خارج الفئة**: إذا حاولت الوصول إلى خاصية محمية من كائن للفئة، ستحصل على خطأ.
- **استخدام "protected" بشكل غير صحيح**: من المهم استخدام "protected" فقط عندما تحتاج إلى السماح للفئات الفرعية بالوصول إلى الخصائص أو الطرق، وإلا يمكنك استخدام "private" لتحقيق مستوى أعلى من الأمان.

### ملاحظات إضافية
- إذا تم إعادة تعريف خاصية محمية في الفئة الفرعية، فإن القيمة الأصلية ستظل محفوظة في الفئة الأصلية.
- "protected" لا تعني أن الخصائص أو الطرق محظورة تمامًا، بل تحدد مستوى وصولها.

## ملخص جملة واحدة
الكلمة المحجوزة "protected" في PHP تُستخدم لتحديد الخصائص والطرق التي يمكن الوصول إليها فقط من داخل الفئة نفسها أو من الفئات المشتقة منها.