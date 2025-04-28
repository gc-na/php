<!--
Meta Description: # Tìm hiểu về lệnh "include" trong PHP: Cách sử dụng và ví dụ ## Tóm tắt Lệnh "include" trong PHP cho phép bạn nhúng một tệp PHP khác vào trong tệp hi...
Meta Keywords: php, tệp, include, lệnh, dụng
-->

# Tìm hiểu về lệnh "include" trong PHP: Cách sử dụng và ví dụ

## Tóm tắt
Lệnh "include" trong PHP cho phép bạn nhúng một tệp PHP khác vào trong tệp hiện tại, giúp tái sử dụng mã và tổ chức dự án một cách hiệu quả.

## Tài liệu
Lệnh `include` là một trong những cách phổ biến nhất để nhúng tệp trong PHP. Khi bạn sử dụng lệnh này, nội dung của tệp được chỉ định sẽ được chèn vào tệp hiện tại tại vị trí mà lệnh `include` được gọi. 

### Mục đích
- Giúp chia nhỏ mã nguồn thành những phần dễ quản lý.
- Cải thiện khả năng tái sử dụng mã.
- Giúp quản lý các tệp cấu hình, hàm, hoặc các đoạn mã chung cho nhiều tệp khác nhau.

### Cách sử dụng
Cú pháp của lệnh `include` như sau:
```php
include 'duong_dan_toi_tap_tin.php';
```

Nếu tệp không tồn tại, PHP sẽ cảnh báo nhưng chương trình vẫn tiếp tục thực thi. 

### Chi tiết
- **Đường dẫn tương đối và tuyệt đối**: Bạn có thể sử dụng cả đường dẫn tương đối và tuyệt đối để chỉ định tệp.
- **Sự khác nhau với require**: Lệnh `include` sẽ không dừng chương trình nếu tệp không tìm thấy, trong khi `require` sẽ gây ra lỗi fatel, dừng chương trình ngay lập tức.
- **Nội dung được nhúng**: Nội dung của tệp được nhúng sẽ được thực thi như thể nó là một phần của tệp hiện tại.

## Ví dụ
### Ví dụ cơ bản
```php
// file1.php
echo "Đây là nội dung của file1.";

// file2.php
include 'file1.php';  // Kết quả: Đây là nội dung của file1.
```

### Ví dụ với đường dẫn tuyệt đối
```php
// file3.php
include '/path/to/your/file1.php';
```

### Ví dụ với điều kiện
```php
if (file_exists('file1.php')) {
    include 'file1.php';
} else {
    echo "Tệp không tồn tại.";
}
```

## Giải thích
Một số vấn đề thường gặp khi sử dụng lệnh `include`:
- **Lỗi đường dẫn**: Đảm bảo rằng đường dẫn đến tệp là chính xác để tránh cảnh báo.
- **Nội dung trùng lặp**: Nếu bạn gọi `include` nhiều lần cho cùng một tệp, nội dung đó sẽ được thực thi lại. Để tránh điều này, bạn có thể sử dụng `include_once` hoặc `require_once`.
- **Thứ tự thực thi**: Nội dung được nhúng sẽ được thực thi ngay khi PHP đạt đến lệnh `include`, vì vậy bạn cần đảm bảo rằng thứ tự của mã là hợp lý.

## Tóm tắt một dòng
Lệnh `include` trong PHP cho phép bạn nhúng tệp PHP khác vào trong tệp hiện tại, giúp tổ chức mã nguồn và tái sử dụng hiệu quả.