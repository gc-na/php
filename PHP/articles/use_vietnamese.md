<!--
Meta Description: # Cách Sử Dụng Lệnh "use" trong PHP: Hướng Dẫn Chi Tiết và Ví Dụ ## Tóm Tắt Lệnh "use" trong PHP cho phép bạn nhập các không gian tên (namespace) và l...
Meta Keywords: tên, use, không, dụng, lớp
-->

# Cách Sử Dụng Lệnh "use" trong PHP: Hướng Dẫn Chi Tiết và Ví Dụ

## Tóm Tắt
Lệnh "use" trong PHP cho phép bạn nhập các không gian tên (namespace) và lớp (class) vào phạm vi hiện tại, giúp tối ưu hóa mã nguồn và giảm thiểu xung đột tên.

## Tài Liệu
Lệnh `use` trong PHP được sử dụng để nhập các lớp, giao diện, hoặc không gian tên vào một tệp PHP, cho phép lập trình viên dễ dàng truy cập và sử dụng mà không cần phải viết đầy đủ tên lớp hoặc không gian tên. 

### Mục Đích
- **Giảm sự lặp lại**: Khi bạn cần sử dụng một lớp từ không gian tên khác, lệnh `use` giúp bạn không cần phải viết lại toàn bộ đường dẫn.
- **Giảm xung đột tên**: Khi có nhiều lớp cùng tên trong các không gian tên khác nhau, bạn có thể sử dụng `use` để xác định rõ ràng lớp nào bạn muốn sử dụng.

### Cách Sử Dụng
```php
use Namespace\ClassName;
```
Bạn có thể nhập nhiều lớp hoặc không gian tên bằng cách phân tách chúng bằng dấu phẩy:
```php
use Namespace\ClassName1;
use Namespace\ClassName2;
```

## Ví Dụ
### Ví dụ 1: Nhập một lớp đơn giản
```php
namespace MyApp;

use OtherNamespace\MyClass;

$instance = new MyClass();
```

### Ví dụ 2: Nhập nhiều lớp
```php
namespace MyApp;

use OtherNamespace\ClassOne;
use OtherNamespace\ClassTwo;

$objectOne = new ClassOne();
$objectTwo = new ClassTwo();
```

### Ví dụ 3: Nhập với bí danh
```php
namespace MyApp;

use OtherNamespace\MyClass as AliasClass;

$instance = new AliasClass();
```

## Giải Thích
Khi sử dụng lệnh `use`, có một số điều cần lưu ý:
- **Xung đột tên**: Nếu hai lớp từ hai không gian tên khác nhau có cùng tên, bạn có thể sử dụng bí danh với `as` để phân biệt chúng.
- **Vị trí**: Lệnh `use` phải được đặt ở đầu tệp PHP, sau khai báo không gian tên (nếu có).
- **Không gian tên áp dụng**: Lệnh `use` chỉ có tác dụng trong tệp mà nó được định nghĩa. Bạn cần phải nhập lại trong mỗi tệp nếu cần sử dụng lớp từ không gian tên khác.

## Tóm Tắt Một Dòng
Lệnh `use` trong PHP giúp bạn nhập lớp và không gian tên, giảm xung đột và cải thiện khả năng đọc của mã nguồn.