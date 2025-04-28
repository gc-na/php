<!--
Meta Description: # Danh Sách (List) trong PHP: Hướng dẫn và Ví dụ sử dụng ## Tóm tắt Trong PHP, `list()` là một cấu trúc ngôn ngữ cho phép bạn gán nhiều biến cùng một ...
Meta Keywords: mảng, các, list, gán, giá
-->

# Danh Sách (List) trong PHP: Hướng dẫn và Ví dụ sử dụng

## Tóm tắt
Trong PHP, `list()` là một cấu trúc ngôn ngữ cho phép bạn gán nhiều biến cùng một lúc từ một mảng. Điều này giúp đơn giản hóa việc truy xuất dữ liệu từ các mảng và tạo ra mã dễ đọc hơn.

## Tài liệu
### Mục đích
`list()` được sử dụng để gán các giá trị từ một mảng tới các biến. Cấu trúc này chỉ hoạt động với mảng số nguyên và không thể sử dụng cho các mảng liên kết.

### Cú pháp
```php
list($var1, $var2, $var3, ...) = $array;
```
- `$var1`, `$var2`, `$var3`, ... là các biến mà bạn muốn gán giá trị từ mảng.
- `$array` là mảng chứa các giá trị bạn muốn gán.

### Chi tiết
- `list()` chỉ có thể gán giá trị từ các mảng số nguyên, không hỗ trợ cho các mảng liên kết.
- Nếu mảng không có đủ phần tử, các biến chưa được gán sẽ có giá trị `NULL`.
- `list()` có thể được sử dụng trong các hàm như `explode()` để dễ dàng gán giá trị từ chuỗi.

## Ví dụ
### Ví dụ cơ bản
```php
$array = ['John', 'Doe', 30];
list($firstName, $lastName, $age) = $array;

echo $firstName; // John
echo $lastName;  // Doe
echo $age;       // 30
```

### Ví dụ với hàm `explode()`
```php
$string = "apple,banana,cherry";
list($fruit1, $fruit2, $fruit3) = explode(",", $string);

echo $fruit1; // apple
echo $fruit2; // banana
echo $fruit3; // cherry
```

## Giải thích
### Những cạm bẫy phổ biến
- **Không hỗ trợ mảng liên kết**: Nếu bạn cố gắng sử dụng `list()` với mảng liên kết, PHP sẽ không gán giá trị và có thể gây ra nhầm lẫn.
- **Số lượng phần tử không đủ**: Nếu số lượng phần tử trong mảng không đủ để gán cho tất cả các biến, những biến không được gán sẽ có giá trị `NULL`, điều này có thể gây ra lỗi logic trong chương trình.

### Lưu ý thêm
- Bạn có thể sử dụng dấu ngoặc để nhóm các giá trị nếu cần.
- `list()` chỉ hoạt động với mảng, không thể sử dụng với các giá trị đơn lẻ hoặc các kiểu dữ liệu khác.

## Tóm tắt một dòng
`list()` trong PHP cho phép gán nhiều biến từ một mảng số nguyên, giúp mã trở nên ngắn gọn và dễ đọc hơn.