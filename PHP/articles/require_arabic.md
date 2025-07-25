<!--
Meta Description: # استخدام الأمر require في PHP: التضمين الأساسي للملفات ## ملخص الأمر `require` في PHP يُستخدم لتضمين ملف آخر داخل ملف PHP الحالي. يعتبر هذا الأمر أدا...
Meta Keywords: php, require, الملف, الأمر, استخدام
-->

# استخدام الأمر require في PHP: التضمين الأساسي للملفات

## ملخص
الأمر `require` في PHP يُستخدم لتضمين ملف آخر داخل ملف PHP الحالي. يعتبر هذا الأمر أداة قوية لتنظيم الكود وإعادة استخدامه، مما يسهل إدارة التطبيقات المعقدة.

## الوثائق
### الغرض
يهدف الأمر `require` إلى إدراج ملف PHP آخر، مما يسمح للمطورين بتنظيم الكود بشكل أفضل. عند استخدام `require`، يتم تنفيذ محتويات الملف المضمن كما لو كانت جزءًا من الملف الحالي.

### الاستخدام
يتطلب الأمر `require` مسار الملف المراد تضمينه. إذا كان الملف غير موجود، سيؤدي ذلك إلى حدوث خطأ فادح (fatal error) وإيقاف تنفيذ البرنامج.

### صيغة الاستخدام
```php
require 'path/to/your/file.php';
```

### تفاصيل
- **المسار النسبي والمطلق**: يمكن استخدام مسار نسبي أو مطلق.
- **تكرار التضمين**: يتم تضمين الملف مرة واحدة فقط عند استخدام `require`. إذا تم تضمينه مرة أخرى، فلن يتم تنفيذه مجددًا. 
- **الفرق بين require وinclude**: `require` يتسبب في خطأ فادح عند عدم وجود الملف، بينما `include` يتسبب في تحذير فقط، مما يسمح بمتابعة تنفيذ البرنامج.

## أمثلة
### مثال 1: تضمين ملف بسيط
```php
// file1.php
echo "Hello, World!";

// file2.php
require 'file1.php';
```
النتيجة: ستظهر "Hello, World!" عند تنفيذ `file2.php`.

### مثال 2: استخدام مسار نسبي
```php
// في ملف index.php
require 'includes/header.php';
```
هنا، يتم تضمين ملف `header.php` الموجود داخل مجلد `includes`.

### مثال 3: التعامل مع الأخطاء
```php
// file3.php
require 'non_existent_file.php'; // سيؤدي هذا إلى خطأ فادح
```
نتيجة هذا الأمر ستكون خطأ فادح يمنع تنفيذ البرنامج.

## الشرح
### الأخطاء الشائعة
- **عدم وجود الملف**: تأكد دائمًا من وجود الملف قبل استخدام `require`، وإلا ستتوقف عملية التنفيذ.
- **المسارات الخاطئة**: تأكد من صحة المسار، سواء كان نسبيًا أو مطلقًا.

### نقاط يجب الانتباه إليها
- استخدم `require_once` بدلاً من `require` إذا كنت ترغب في تجنب تضمين نفس الملف أكثر من مرة.
- تأكد من إدارة الأخطاء بشكل جيد، خاصة عند تضمين الملفات التي قد لا تكون موجودة.

## ملخص بجملة واحدة
الأمر `require` في PHP يُستخدم لتضمين ملفات أخرى، مما يسهل تنظيم الكود وإعادة استخدامه، مع الأخذ في الاعتبار أن عدم وجود الملف سيؤدي إلى خطأ فادح.