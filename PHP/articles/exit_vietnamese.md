<!--
Meta Description: # Lệnh exit trong PHP: Cách thức và Cách sử dụng ## Tóm tắt Lệnh `exit` trong PHP được sử dụng để dừng thực thi của một script. Nó thường được sử dụng...
Meta Keywords: một, exit, được, thoát, khi
-->

# Lệnh exit trong PHP: Cách thức và Cách sử dụng

## Tóm tắt
Lệnh `exit` trong PHP được sử dụng để dừng thực thi của một script. Nó thường được sử dụng để thoát khỏi một chương trình khi gặp lỗi hoặc khi một điều kiện nhất định được đáp ứng.

## Tài liệu
Lệnh `exit` là một trong những lệnh quan trọng trong PHP, cho phép lập trình viên kết thúc quá trình thực thi của một script. `exit` có thể được gọi với một tham số tùy chọn, cho phép bạn truyền một mã lỗi hoặc thông điệp cụ thể.

### Cú pháp
```php
exit([mixed $status]);
```

- `$status` (tùy chọn): Đây có thể là một số nguyên hoặc một chuỗi. Nếu là số nguyên, nó được coi là mã lỗi (thường từ 0 đến 255), nếu là chuỗi, nó sẽ được in ra trước khi thoát.

### Mục đích
- Dừng thực thi script hiện tại.
- Thoát ra với một mã trạng thái hoặc thông báo cho biết lý do thoát.

## Ví dụ
### Ví dụ cơ bản 1: Thoát với mã trạng thái
```php
if (!file_exists("file.txt")) {
    exit(1); // Thoát với mã lỗi 1 nếu file không tồn tại
}
```

### Ví dụ cơ bản 2: Thoát với thông điệp
```php
if (!isset($user)) {
    exit("Người dùng không được xác định."); // Thoát với thông báo
}
```

### Ví dụ cơ bản 3: Thoát khi gặp lỗi
```php
$connection = mysqli_connect("localhost", "user", "password");
if (!$connection) {
    exit("Kết nối thất bại: " . mysqli_connect_error());
}
```

## Giải thích
Khi sử dụng `exit`, có một số điểm cần lưu ý:
- Việc sử dụng `exit` sẽ dừng toàn bộ script, điều này có thể dẫn đến việc không thực hiện được các đoạn mã phía sau.
- Nếu mã trạng thái là một chuỗi, nó sẽ được in ra trên trình duyệt trước khi thoát, điều này có thể gây ra sự khó khăn trong việc xử lý lỗi.
- Sử dụng mã trạng thái 0 thường được coi là thành công, trong khi bất kỳ mã nào khác đều được coi là thất bại.

Khi lập trình, bạn nên cân nhắc kỹ lưỡng trước khi sử dụng `exit`, vì nó sẽ ngừng mọi hoạt động của script ngay lập tức.

## Tóm tắt một dòng
Lệnh `exit` trong PHP cho phép bạn dừng thực thi script và có thể truyền mã lỗi hoặc thông điệp để thông báo lý do thoát.