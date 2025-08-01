<!--
Meta Description: # استخدام elseif في PHP: الدليل الشامل ## ملخص أمر `elseif` في PHP يُستخدم كجزء من التحكم في التدفق، حيث يسمح بتنفيذ كتل معينة من الكود بناءً على شروط...
Meta Keywords: elseif, استخدام, الكود, الشروط, echo
-->

# استخدام elseif في PHP: الدليل الشامل

## ملخص
أمر `elseif` في PHP يُستخدم كجزء من التحكم في التدفق، حيث يسمح بتنفيذ كتل معينة من الكود بناءً على شروط متعددة، مما يعزز من مرونة البرامج ويجعلها أكثر كفاءة.

## الوثائق
### الغرض
يُستخدم `elseif` لتوسيع شرط `if`، مما يتيح للمطورين إضافة شروط إضافية لتحديد مسارات مختلفة من التنفيذ بناءً على النتائج المختلفة.

### الاستخدام
تتبع بنية `elseif` الصيغة التالية:

```php
if (condition1) {
    // تنفيذ الكود إذا كانت condition1 صحيحة
} elseif (condition2) {
    // تنفيذ الكود إذا كانت condition2 صحيحة
} else {
    // تنفيذ الكود إذا لم تكن أي من الشروط السابقة صحيحة
}
```

### التفاصيل
1. **التسلسل**: يتم تقييم الشروط من الأعلى إلى الأسفل، وعندما يتحقق شرط، يتم تنفيذ الكود المرتبط به، ويتجاهل باقي الشروط.
2. **الشرط الافتراضي**: يمكن استخدام `else` بعد `if` و `elseif` لتقديم حالة افتراضية إذا لم تكن أي من الشروط السابقة صحيحة.
3. **التعشيش**: يمكن استخدام `elseif` داخل كتل `if`، مما يسمح بإنشاء شروط معقدة.

## الأمثلة
### مثال 1: استخدام elseif بسيط
```php
$عدد = 10;

if ($عدد < 5) {
    echo "العدد أقل من 5";
} elseif ($عدد == 10) {
    echo "العدد يساوي 10";
} else {
    echo "العدد أكبر من 5";
}
```

### مثال 2: التعشيش
```php
$درجة = 85;

if ($درجة >= 90) {
    echo "ممتاز";
} elseif ($درجة >= 80) {
    echo "جيد جداً";
} elseif ($درجة >= 70) {
    echo "جيد";
} else {
    echo "مقبول";
}
```

## الشرح
### الأخطاء الشائعة
- **نسيان الأقواس**: يجب التأكد من استخدام الأقواس بشكل صحيح حول الشروط.
- **عدم استخدام `else`**: إذا كانت هناك حاجة للتعامل مع جميع الحالات، فمن المهم استخدام `else` أيضًا.
- **الخلط بين `=` و `==`**: يجب الانتباه إلى الفرق بين عملية الإسناد (`=`) وعملية المقارنة (`==`).

### ملاحظات إضافية
- يمكن استخدام `switch` كبديل لـ `if` و `elseif` في بعض الحالات، خاصةً عندما تكون الشروط تعتمد على قيمة واحدة.
- تذكر أن استخدام `elseif` بشكل مفرط قد يجعل الكود صعب القراءة. تأكد من تنظيم الشروط بشكل منطقي.

## ملخص جملة واحدة
يُستخدم أمر `elseif` في PHP لإضافة شروط إضافية ضمن التحكم في التدفق، مما يوفر مرونة في تنفيذ الكود بناءً على شروط متعددة.