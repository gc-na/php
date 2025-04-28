<!--
Meta Description: # Tên miền (Namespace) trong PHP: Tổ Chức và Quản Lý Mã Nguồn ## Tóm tắt Tên miền (namespace) trong PHP là một tính năng giúp tổ chức mã nguồn, ngăn c...
Meta Keywords: namespace, tên, dụng, miền, trong
-->

# Tên miền (Namespace) trong PHP: Tổ Chức và Quản Lý Mã Nguồn

## Tóm tắt
Tên miền (namespace) trong PHP là một tính năng giúp tổ chức mã nguồn, ngăn chặn xung đột tên giữa các lớp, hàm và hằng số trong các ứng dụng lớn.

## Tài liệu

### Mục đích
Tên miền (namespace) cho phép lập trình viên nhóm các lớp, hàm, và hằng số lại với nhau trong một không gian tên duy nhất, từ đó giúp quản lý mã nguồn dễ dàng hơn và giảm thiểu khả năng xung đột tên.

### Sử dụng
Để khai báo một namespace, bạn sử dụng từ khóa `namespace` theo sau là tên miền mà bạn muốn xác định. Tên miền có thể bao gồm các phần cách nhau bằng dấu gạch chéo (`\`). Ví dụ:

```php
namespace MyApp\Models;
```

Tất cả các lớp, hàm, và hằng số được định nghĩa sau dòng khai báo `namespace` sẽ thuộc về không gian tên này.

### Chi tiết
- **Khai báo Namespace**: Bạn có thể khai báo namespace ở đầu tệp PHP.
- **Sử dụng Namespace**: Để sử dụng một lớp hoặc hàm trong namespace khác, bạn cần chỉ rõ tên miền đầy đủ hoặc sử dụng từ khóa `use`.
- **Xung đột Tên**: Nếu bạn có hai lớp cùng tên trong các namespace khác nhau, bạn có thể sử dụng tên miền đầy đủ để phân biệt chúng.

## Ví dụ

### 1. Khai báo và sử dụng namespace

```php
namespace MyApp\Models;

class User {
    public function getName() {
        return "John Doe";
    }
}
```

```php
namespace MyApp\Controllers;

use MyApp\Models\User;

$user = new User();
echo $user->getName(); // Kết quả: John Doe
```

### 2. Xung đột tên

```php
namespace MyApp\Models;

class User {
    // ...
}

namespace MyApp\Controllers;

class User {
    // ...
}

// Sử dụng lớp User từ Models
$modelUser = new \MyApp\Models\User();
```

## Giải thích
- **Xung đột tên**: Khi có nhiều lớp, hàm, hoặc hằng số cùng tên nhưng thuộc các namespace khác nhau, bạn cần phải chỉ định rõ ràng tên miền để tránh sai sót.
- **Tính dễ đọc**: Việc sử dụng namespace giúp mã nguồn trở nên rõ ràng hơn và dễ bảo trì hơn, đặc biệt là trong các dự án lớn.
- **Không gian tên mặc định**: Nếu không khai báo namespace, mã nguồn sẽ thuộc về không gian tên toàn cục.

## Tóm tắt một câu
Tên miền (namespace) trong PHP là công cụ hữu ích để tổ chức mã nguồn và tránh xung đột giữa các thành phần trong ứng dụng.