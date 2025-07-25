<!--
Meta Description: # استخدام الأمر "yield" في PHP: دليل شامل ## ملخص الأمر "yield" في PHP يُستخدم لإنشاء مولدات (Generators) تسمح بتوليد القيم بشكل متتابع دون الحاجة لتخ...
Meta Keywords: yield, القيم, استخدام, البيانات, php
-->

# استخدام الأمر "yield" في PHP: دليل شامل

## ملخص
الأمر "yield" في PHP يُستخدم لإنشاء مولدات (Generators) تسمح بتوليد القيم بشكل متتابع دون الحاجة لتخزين جميع القيم في الذاكرة، مما يوفر كفاءة في استخدام الذاكرة ويسهل التعامل مع مجموعات البيانات الكبيرة.

## الوثائق
### الغرض
يُستخدم الأمر "yield" في PHP لإرجاع القيم من دالة بطريقة متتابعة، مما يمكّن المطورين من التعامل مع مجموعات ضخمة من البيانات بشكل أكثر كفاءة. بدلاً من استخدام دالة "return" التي تُرجع القيمة وتُنهي تنفيذ الدالة، يُستخدم "yield" لإرجاع قيمة واحدة في كل مرة تُستدعى فيها الدالة.

### الاستخدام
يتم استخدام "yield" داخل الدوال لتعريف مولد. عند استدعاء المولد، يتم تنفيذ الكود حتى تصل الدالة إلى "yield"، حيث تُرجع القيمة الحالية وتوقف تنفيذ الدالة حتى يتم استدعاء المولد مرة أخرى.

### التفاصيل
1. **المولدات**: الدوال التي تحتوي على "yield" تُعتبر مولدات، ويمكن استخدامها مع حلقة `foreach`.
2. **الكفاءة**: استخدام "yield" يساعد في تقليل استخدام الذاكرة، حيث يتم تحميل القيم عند الحاجة فقط.
3. **تدفق البيانات**: المولدات تُساعد في معالجة البيانات بشكل تتابعي، مما يُسهل العمل مع البيانات الكبيرة أو البيانات التي تأتي من مصادر خارجية مثل قواعد البيانات أو واجهات برمجة التطبيقات.

## أمثلة
### مثال أساسي
```php
function numberGenerator() {
    for ($i = 1; $i <= 5; $i++) {
        yield $i;
    }
}

foreach (numberGenerator() as $number) {
    echo $number . "\n";
}
```
**النتيجة:**
```
1
2
3
4
5
```

### مثال مع القيم المعقدة
```php
function fibonacci($n) {
    $a = 0;
    $b = 1;
    for ($i = 0; $i < $n; $i++) {
        yield $a;
        $temp = $a;
        $a = $b;
        $b = $temp + $b;
    }
}

foreach (fibonacci(10) as $value) {
    echo $value . "\n";
}
```
**النتيجة:**
```
0
1
1
2
3
5
8
13
21
34
```

## الشرح
### الأخطاء الشائعة
- **عدم استخدام `foreach`**: عند محاولة استخدام المولد مباشرة دون استخدام حلقة `foreach`، لن يتم استرداد أي قيمة.
- **تخزين القيم**: بعض المطورين يعتقدون أن المولدات تخزن القيم في الذاكرة مثل المصفوفات، ولكنها تُرجع القيم عند الطلب فقط.

### ملاحظات إضافية
- يمكن استخدام الأمر "yield" مع المعاملات مثل `yield from`، مما يسمح بإرجاع القيم من مولد آخر.
- يجب الانتباه إلى أن المولدات لا تعيد القيم إلى الدالة، بل تُعيد التحكم إلى نقطة معينة في الدالة.

## ملخص من سطر واحد
الأمر "yield" في PHP يُستخدم لإنشاء مولدات تتيح إرجاع القيم بشكل متتابع وكفء، مما يسهل التعامل مع البيانات الكبيرة.