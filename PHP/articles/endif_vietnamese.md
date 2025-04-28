<!--
Meta Description: # Sử dụng "endif" trong PHP: Cách viết cấu trúc điều kiện rõ ràng ## Tóm tắt `endif` là một cú pháp trong PHP được sử dụng để kết thúc một cấu trúc đi...
Meta Keywords: endif, dụng, trong, php, pháp
-->

# Sử dụng "endif" trong PHP: Cách viết cấu trúc điều kiện rõ ràng

## Tóm tắt
`endif` là một cú pháp trong PHP được sử dụng để kết thúc một cấu trúc điều kiện `if` khi bạn viết mã theo dạng cú pháp không ngoặc nhọn. Điều này giúp mã của bạn trở nên dễ đọc hơn trong những trường hợp nhất định.

## Tài liệu
### Mục đích
`endif` được sử dụng để kết thúc khối lệnh của câu lệnh điều kiện `if` trong PHP. Khi bạn không sử dụng dấu ngoặc nhọn `{}` để bao quanh các lệnh bên trong khối `if`, bạn có thể dùng `endif` để chỉ rõ điểm kết thúc của khối.

### Cách sử dụng
Cú pháp của `endif` có thể được sử dụng như sau:

```php
if (điều kiện):
    // Các lệnh thực thi nếu điều kiện đúng
endif;
```

Trong trường hợp này, khi điều kiện được thỏa mãn, các lệnh bên trong sẽ được thực thi cho đến khi `endif` được gặp.

### Chi tiết
- `endif` là một phần của cú pháp ngắn gọn trong PHP, cho phép bạn sử dụng `if`, `else`, `elseif`, và `endif` mà không cần sử dụng dấu ngoặc nhọn.
- Cú pháp này thường được sử dụng trong các tệp HTML nhúng PHP, giúp tăng tính dễ đọc cho mã nguồn.

## Ví dụ
### Ví dụ 1: Sử dụng `endif` cơ bản
```php
$number = 10;

if ($number > 5):
    echo "Số lớn hơn 5";
endif;
```

### Ví dụ 2: Sử dụng `else` với `endif`
```php
$number = 3;

if ($number > 5):
    echo "Số lớn hơn 5";
else:
    echo "Số không lớn hơn 5";
endif;
```

### Ví dụ 3: Sử dụng `elseif` với `endif`
```php
$number = 5;

if ($number > 5):
    echo "Số lớn hơn 5";
elseif ($number == 5):
    echo "Số bằng 5";
else:
    echo "Số nhỏ hơn 5";
endif;
```

## Giải thích
- **Cú pháp không chính xác**: Một số lập trình viên mới có thể quên không sử dụng dấu hai chấm `:` sau điều kiện `if`, dẫn đến lỗi cú pháp.
- **Nhầm lẫn giữa cú pháp**: Sử dụng cú pháp `endif` không thể thay thế cho cấu trúc điều kiện với dấu ngoặc nhọn. Bạn nên chọn một trong hai cách để giữ cho mã nguồn nhất quán.
- **Tính tương thích**: Cú pháp của `endif` được hỗ trợ từ phiên bản PHP 5 và không có sự thay đổi lớn trong các phiên bản sau.

## Tóm tắt một dòng
`endif` trong PHP là cú pháp dùng để kết thúc khối lệnh của câu lệnh điều kiện `if` mà không cần dùng dấu ngoặc nhọn, giúp mã dễ đọc hơn.