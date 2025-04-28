<!--
Meta Description: # Hướng Dẫn Chi Tiết Về Lệnh "require" Trong PHP ## Tóm Tắt Lệnh `require` trong PHP được sử dụng để bao gồm và thực thi một file PHP khác. Nếu file k...
Meta Keywords: php, file, không, require, bao
-->

# Hướng Dẫn Chi Tiết Về Lệnh "require" Trong PHP

## Tóm Tắt
Lệnh `require` trong PHP được sử dụng để bao gồm và thực thi một file PHP khác. Nếu file không tồn tại hoặc không thể được mở, PHP sẽ dừng thực thi và báo lỗi.

## Tài Liệu
### Mục Đích
Lệnh `require` cho phép lập trình viên tổ chức mã nguồn bằng cách chia nhỏ thành nhiều file. Điều này không chỉ giúp dễ dàng quản lý mà còn tăng tính tái sử dụng của mã.

### Cách Sử Dụng
Cú pháp cơ bản của lệnh `require` như sau:

```php
require 'path/to/file.php';
```

- **path/to/file.php**: Đường dẫn đến file PHP bạn muốn bao gồm. Đường dẫn có thể là tương đối hoặc tuyệt đối.

### Chi Tiết
- Nếu file được yêu cầu không tồn tại, PHP sẽ phát sinh một lỗi fatal và dừng thực thi mã.
- `require` khác với `include` ở chỗ nếu file không tồn tại, `include` sẽ chỉ cảnh báo và tiếp tục thực thi mã còn lại.
- Lệnh `require` có thể được sử dụng trong bất kỳ phần nào của mã, bao gồm trong các hàm, lớp, và thậm chí trong các file khác.
- Để bao gồm một file chỉ một lần, lập trình viên có thể sử dụng `require_once`, điều này giúp tránh việc bao gồm file nhiều lần gây ra lỗi.

## Ví Dụ
### Ví dụ 1: Bao gồm một file đơn giản
```php
// file1.php
echo "Chào mừng đến với PHP!";

// file2.php
require 'file1.php'; // Kết quả: Chào mừng đến với PHP!
```

### Ví dụ 2: Xử lý lỗi khi file không tồn tại
```php
// file3.php
require 'file_not_exist.php'; // Lỗi fatal sẽ xảy ra nếu file không tồn tại
```

### Ví dụ 3: Sử dụng require_once
```php
// file4.php
require_once 'file1.php'; // Chỉ bao gồm file1.php một lần, tránh lỗi nếu gọi lại
require_once 'file1.php'; // Không có lỗi xảy ra
```

## Giải Thích
- **Lỗi Fatal**: Nếu không tìm thấy file, PHP sẽ dừng lại và thông báo lỗi. Điều này có thể gây ra vấn đề trong ứng dụng nếu không được xử lý đúng cách.
- **Hiệu Suất**: Sử dụng `require_once` có thể làm giảm hiệu suất nếu bạn có nhiều file lớn sẽ được bao gồm nhiều lần, tuy nhiên, nó giúp tránh lỗi do bao gồm trùng lặp.
- **Đường Dẫn**: Đảm bảo đường dẫn tới file là chính xác. Sử dụng đường dẫn tuyệt đối (hoặc tương đối từ thư mục gốc) sẽ giúp tránh được vấn đề khi thay đổi vị trí file.

## Tóm Tắt Một Dòng
Lệnh `require` trong PHP cho phép bạn bao gồm và thực thi một file PHP khác, ngăn chặn việc thực thi mã nếu file không tồn tại.