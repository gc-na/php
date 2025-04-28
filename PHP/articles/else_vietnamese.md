<!--
Meta Description: # Câu lệnh "else" trong PHP: Hướng dẫn chi tiết và ví dụ ## Tóm tắt Câu lệnh "else" trong PHP được sử dụng để thực hiện một khối mã khác nếu điều kiện...
Meta Keywords: else, câu, lệnh, điều, kiện
-->

# Câu lệnh "else" trong PHP: Hướng dẫn chi tiết và ví dụ

## Tóm tắt
Câu lệnh "else" trong PHP được sử dụng để thực hiện một khối mã khác nếu điều kiện trong câu lệnh "if" không được đáp ứng. Đây là một phần quan trọng trong lập trình điều kiện, giúp tạo ra các logic phức tạp hơn trong ứng dụng.

## Tài liệu
Câu lệnh "else" cho phép lập trình viên xác định các hành động thay thế khi điều kiện của câu lệnh "if" không đúng. Cấu trúc cơ bản của câu lệnh "else" như sau:

```php
if (điều_kiện) {
    // Khối mã sẽ được thực thi nếu điều kiện đúng
} else {
    // Khối mã sẽ được thực thi nếu điều kiện không đúng
}
```

### Mục đích
Mục đích chính của "else" là cung cấp lựa chọn khác cho các tình huống mà điều kiện không được đáp ứng, giúp tăng cường tính linh hoạt trong mã nguồn.

### Cách sử dụng
- Câu lệnh "else" luôn đi kèm với câu lệnh "if".
- Có thể sử dụng nhiều câu lệnh "else if" để kiểm tra nhiều điều kiện khác nhau.

## Ví dụ
### Ví dụ cơ bản
```php
$tuoi = 20;

if ($tuoi >= 18) {
    echo "Bạn đã đủ tuổi trưởng thành.";
} else {
    echo "Bạn chưa đủ tuổi trưởng thành.";
}
```
Kết quả: "Bạn đã đủ tuổi trưởng thành."

### Ví dụ với else if
```php
$diem = 75;

if ($diem >= 90) {
    echo "Xuất sắc";
} else if ($diem >= 75) {
    echo "Khá";
} else {
    echo "Cần cải thiện";
}
```
Kết quả: "Khá"

## Giải thích
Khi sử dụng câu lệnh "else", có một số điểm cần lưu ý:
- Tránh lồng ghép quá nhiều câu lệnh "if" và "else" vì có thể làm cho mã trở nên khó đọc và bảo trì.
- Đảm bảo rằng các điều kiện trong "else if" được sắp xếp theo thứ tự logic để tránh bỏ lỡ các điều kiện quan trọng.

## Tóm tắt một dòng
Câu lệnh "else" trong PHP cho phép xử lý các trường hợp khi điều kiện trong câu lệnh "if" không đúng, giúp tăng tính linh hoạt trong lập trình điều kiện.