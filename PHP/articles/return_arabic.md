<!--
Meta Description: # الأمر "return" في PHP: كيفية استخدامه بفعالية ## ملخص الأمر "return" في PHP يُستخدم لإنهاء تنفيذ دالة وإرجاع قيمة إلى المكان الذي تم استدعاؤها منه. ...
Meta Keywords: return, php, استخدام, القيمة, تنفيذ
-->

# الأمر "return" في PHP: كيفية استخدامه بفعالية

## ملخص
الأمر "return" في PHP يُستخدم لإنهاء تنفيذ دالة وإرجاع قيمة إلى المكان الذي تم استدعاؤها منه. يُعتبر من الأدوات الأساسية في البرمجة بلغة PHP.

## الوثائق
### الغرض
الأمر "return" يُستخدم ضمن دوال PHP لإرجاع قيمة إلى المرسل، مما يسمح بإنتاج نتائج من الدوال لاستخدامها لاحقًا في البرنامج.

### الاستخدام
يتم استخدام "return" في أي دالة أو ميثود في PHP. عندما يتم استدعاء الدالة، يتوقف التنفيذ عند جملة "return" ويتم إرجاع القيمة المحددة.

### التفاصيل
- **صيغة الاستخدام**: 
  ```php
  return [القيمة];
  ```
- **نوع القيمة**: يمكن أن تكون القيمة المُرجعة من أي نوع بيانات، بما في ذلك الأعداد، السلاسل النصية، المصفوفات، والكائنات.
- **التوقف عن التنفيذ**: بعد تنفيذ جملة "return"، يتوقف تنفيذ الدالة، ولا يتم تنفيذ أي كود بعدها.

## أمثلة
### مثال 1: إرجاع عدد
```php
function جمع($أ, $ب) {
    return $أ + $ب;
}

$result = جمع(5, 3);
echo $result; // الناتج: 8
```

### مثال 2: إرجاع سلسلة نصية
```php
function مرحباً($اسم) {
    return "مرحبًا، " . $اسم;
}

echo مرحباً("أحمد"); // الناتج: مرحبًا، أحمد
```

### مثال 3: إرجاع مصفوفة
```php
function الحصول_على_المعلومات() {
    return ['اسم' => 'علي', 'عمر' => 30];
}

$info = الحصول_على_المعلومات();
echo $info['اسم']; // الناتج: علي
```

## الشرح
### الفخاخ الشائعة
- **عدم استخدام return**: في حالة عدم استخدام "return" في دالة، فإنها ستعيد القيمة `NULL` بشكل افتراضي.
- **تعدد أوامر return**: يمكن استخدام أكثر من جملة "return" في الدالة، لكن التنفيذ سيتوقف عند أول جملة "return" يتم الوصول إليها.
- **تداخل الدوال**: يمكن استخدام القيمة المُرجعة من دالة كمدخل لدالة أخرى.

### ملاحظات إضافية
- يجب التفكير في نوع البيانات المُرجعة لضمان تطابقها مع ما يتوقعه البرنامج.
- استخدام "return" بشكل صحيح يمكن أن يحسن من قراءة الكود ويساعد في تنظيم البرامج المعقدة.

## ملخص جملة واحدة
الأمر "return" في PHP يُستخدم لإنهاء تنفيذ الدالة وإرجاع قيمة، مما يسهل استخدام النتائج في أجزاء أخرى من البرنامج.