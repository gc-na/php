<!--
Meta Description: # قائمة PHP: استخدامات وأمثلة ## ملخص تعتبر دالة "list" في PHP وسيلة فعالة لربط القيم في مصفوفة بأسماء المتغيرات، مما يسهل على المطورين التعامل مع الب...
Meta Keywords: list, php, استخدام, المصفوفات, على
-->

# قائمة PHP: استخدامات وأمثلة

## ملخص
تعتبر دالة "list" في PHP وسيلة فعالة لربط القيم في مصفوفة بأسماء المتغيرات، مما يسهل على المطورين التعامل مع البيانات بشكل منظم.

## الوثائق
### الغرض
دالة "list" تُستخدم لتهيئة مجموعة من المتغيرات بقيم من مصفوفة. هذه الطريقة مفيدة عند التعامل مع المصفوفات المتعددة الأبعاد أو عند الحصول على قيم من دوال تُرجع مصفوفات.

### الاستخدام
يمكن استخدام "list" فقط مع المصفوفات، ويجب أن تكون المصفوفة مرتبة من حيث القيم. تُستخدم الدالة بالصيغة التالية:

```php
list($var1, $var2, $var3) = $array;
```

### التفاصيل
- **الإصدار**: تدعم "list" من إصدار PHP 4 وما بعده.
- **القيود**: يجب أن تكون المصفوفة رقمية أو متسلسلة. لا يمكن استخدام "list" مع المصفوفات المرتبطة.
- **التوافق**: تعمل بشكل جيد مع المصفوفات التي تحتوي على قيم ثابتة أو نتيجة دوال.

## الأمثلة
### مثال 1: استخدام "list" مع مصفوفة بسيطة
```php
$array = ['أحمر', 'أخضر', 'أزرق'];
list($color1, $color2, $color3) = $array;

echo $color1; // يطبع: أحمر
```

### مثال 2: استخدام "list" مع دالة
```php
function getCoordinates() {
    return [10, 20];
}

list($x, $y) = getCoordinates();

echo $x; // يطبع: 10
echo $y; // يطبع: 20
```

### مثال 3: استخدام "list" مع مصفوفة متعددة الأبعاد
```php
$users = [
    ['أحمد', 25],
    ['سارة', 30],
];

foreach ($users as $user) {
    list($name, $age) = $user;
    echo "$name هو $age سنة.\n"; // يطبع: أحمد هو 25 سنة. ثم سارة هي 30 سنة.
}
```

## الشرح
### الأخطاء الشائعة
- **عدم توافق البيانات**: إذا كانت المصفوفة لا تحتوي على عدد كافٍ من القيم، فلن يتم تهيئة جميع المتغيرات، مما قد يؤدي إلى مشاكل في البرمجة.
- **استخدام غير صحيح**: لا يمكن استخدام "list" مع المصفوفات المرتبطة، وهذا قد يسبب ارتباكاً لدى بعض المطورين.

### ملاحظات إضافية
- يمكن استخدام "list" مع "array destructuring" في PHP 7.1 وما بعدها، مما يجعل التعامل مع المصفوفات أكثر سهولة.

## ملخص
تساعد دالة "list" في PHP على تهيئة المتغيرات من المصفوفات بطريقة منظمة وسهلة، مما يسهل على المطورين التعامل مع البيانات.