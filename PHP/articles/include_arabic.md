<!--
Meta Description: # استخدام الأمر "include" في PHP: كيفية تضمين الملفات في تطبيقات PHP ## ملخص الأمر "include" في PHP يُستخدم لتضمين محتويات ملف آخر داخل ملف PHP، مما ي...
Meta Keywords: php, استخدام, include, ملف, الملف
-->

# استخدام الأمر "include" في PHP: كيفية تضمين الملفات في تطبيقات PHP

## ملخص
الأمر "include" في PHP يُستخدم لتضمين محتويات ملف آخر داخل ملف PHP، مما يسمح بإعادة استخدام الكود وتنظيمه بشكل أفضل.

## الوثائق
### الغرض
يهدف الأمر "include" في PHP إلى دمج محتويات ملف خارجي في ملف PHP الحالي. يُستخدم بشكل شائع لتحميل ملفات تحتوي على دوال أو إعدادات أو واجهات مستخدم، مما يسهل إدارة وصيانة الكود.

### الاستخدام
يمكن استخدام الأمر "include" كالتالي:
```php
include 'filename.php';
```
حيث يتم استبدال `'filename.php'` باسم الملف الذي ترغب في تضمينه. إذا كان الملف غير موجود، سيظهر تحذير ولكن سيتم تنفيذ الشيفرة التالية.

### تفاصيل
- **المسار النسبي والمطلق**: يمكنك استخدام مسارات نسبية أو مطلقة عند تضمين الملفات. على سبيل المثال:
  ```php
  include 'subdirectory/filename.php';
  ```
- **تحذير عند الفشل**: إذا لم يتم العثور على الملف، سيظهر تحذير ولكن لن يتوقف تنفيذ الشيفرة. 
- **استخدام include_once**: إذا كنت ترغب في تضمين الملف مرة واحدة فقط، يمكنك استخدام `include_once`:
  ```php
  include_once 'filename.php';
  ```
  
## أمثلة
### مثال 1: تضمين ملف بسيط
```php
// ملف main.php
include 'header.php';

// بقية الشيفرة
echo "مرحبًا بكم في موقعي!";
```

### مثال 2: استخدام include مع مسار نسبي
```php
include 'includes/functions.php';
```

### مثال 3: استخدام include_once
```php
include_once 'config.php'; // يتم تضمينه مرة واحدة فقط
```

## الشرح
### الأخطاء الشائعة
- **عدم وجود الملف**: إذا كان المسار غير صحيح أو الملف غير موجود، سيظهر تحذير، ولكن الشيفرة ستستمر في التنفيذ.
- **تداخل الملفات**: إذا كان هناك تضمين لملف يحتوي على تعريفات متكررة، قد يؤدي ذلك إلى أخطاء مثل "إعادة تعريف دالة".

### ملاحظات إضافية
- من الأفضل استخدام `include_once` لتجنب مشاكل إعادة التعريف.
- تأكد من استخدام المسارات الصحيحة لتجنب الأخطاء.

## ملخص جملة واحدة
الأمر "include" في PHP يُستخدم لتضمين محتويات ملف خارجي داخل ملف PHP، مما يسهل تنظيم وإعادة استخدام الكود.