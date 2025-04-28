<!--
Meta Description: # نهاية الجملة: استخدام "endswitch" في PHP ## ملخص تُعتبر عبارة "endswitch" جزءًا من بناء جملة switch في PHP، حيث تُستخدم لإنهاء كتلة switch بشكل واضح...
Meta Keywords: endswitch, php, switch, استخدام, case
-->

# نهاية الجملة: استخدام "endswitch" في PHP

## ملخص
تُعتبر عبارة "endswitch" جزءًا من بناء جملة switch في PHP، حيث تُستخدم لإنهاء كتلة switch بشكل واضح ومنظم.

## الوثائق
تُستخدم "endswitch" كطريقة بديلة لإنهاء جملة switch في PHP. بدلاً من استخدام الأقواس المعقوفة `{}`, يمكنك استخدام "endswitch" مع جملة `switch` لتحقيق نفس الهدف، مما يجعل الكود أكثر وضوحًا في بعض الحالات. يتم استخدام "endswitch" عادةً عند كتابة كود HTML مع PHP، مما يجعل الفواصل بين الكود PHP وHTML أكثر وضوحًا.

### التركيب
```php
switch (expression) :
    case value1:
        // كود لتنفيذ إذا كانت التعبير يساوي value1
        break;
    case value2:
        // كود لتنفيذ إذا كانت التعبير يساوي value2
        break;
    default:
        // كود للتنفيذ في حال عدم تطابق أي من القيم السابقة
endswitch;
```

### الغرض
تساعد "endswitch" في تحسين قراءة الكود، خاصة في التطبيقات الكبيرة أو عند تضمين PHP داخل HTML. كما أنها توفر بديلاً واضحًا للأقواس المعقوفة، مما يسهل فهم مكان انتهاء جملة switch.

## الأمثلة
### مثال 1: استخدام endswitch البسيط
```php
<?php
$day = "الأحد";

switch ($day) :
    case "السبت":
        echo "اليوم هو السبت.";
        break;
    case "الأحد":
        echo "اليوم هو الأحد.";
        break;
    default:
        echo "اليوم ليس السبت أو الأحد.";
endswitch;
?>
```

### مثال 2: استخدام endswitch مع HTML
```php
<?php
$color = "أحمر";

switch ($color) :
    case "أخضر":
        echo "<div style='color:green;'>اللون أخضر</div>";
        break;
    case "أحمر":
        echo "<div style='color:red;'>اللون أحمر</div>";
        break;
    default:
        echo "<div style='color:black;'>اللون غير معروف</div>";
endswitch;
?>
```

## التفسير
عند استخدام "endswitch"، يجب الانتباه إلى النقاط التالية:
- تأكد من استخدام النقطتين `:` بعد تعبير switch، بدلاً من الأقواس المعقوفة.
- تذكر أن "endswitch" لا تستخدم مع الجمل الأخرى مثل if أو for، بل فقط مع switch.
- قد يعتبر بعض المطورين "endswitch" أقل شيوعًا من استخدام الأقواس، لذا تأكد من أن فريقك متفق على أسلوب الكتابة المستخدم.

## ملخص بجملة واحدة
"endswitch" هو تعبير يُستخدم لإنهاء جملة switch في PHP بطريقة واضحة ومنظمة.