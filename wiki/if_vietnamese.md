<!--
Meta Description: # Câu lệnh "if" trong PHP: Kiểm tra Điều Kiện Hiệu Quả ## Tóm tắt Câu lệnh "if" trong PHP cho phép lập trình viên kiểm tra một điều kiện và thực hiện ...
Meta Keywords: điều, câu, lệnh, kiện, trong
-->

# Câu lệnh "if" trong PHP: Kiểm tra Điều Kiện Hiệu Quả

## Tóm tắt
Câu lệnh "if" trong PHP cho phép lập trình viên kiểm tra một điều kiện và thực hiện các đoạn mã khác nhau dựa trên kết quả của điều kiện đó. Đây là một trong những cấu trúc điều khiển cơ bản và quan trọng trong lập trình PHP.

## Tài liệu
Câu lệnh "if" trong PHP được sử dụng để thực hiện kiểm tra điều kiện. Nếu điều kiện trả về giá trị true, các câu lệnh bên trong khối "if" sẽ được thực hiện. Cú pháp cơ bản như sau:

```php
if (điều_kiện) {
    // Các câu lệnh sẽ được thực hiện nếu điều kiện là true
}
```

### Cú pháp mở rộng
- **Câu lệnh if-else**: Thực hiện một khối mã nếu điều kiện là true và một khối khác nếu điều kiện là false.
  
```php
if (điều_kiện) {
    // Khối mã nếu điều kiện true
} else {
    // Khối mã nếu điều kiện false
}
```

- **Câu lệnh if-else if-else**: Kiểm tra nhiều điều kiện khác nhau.

```php
if (điều_kiện1) {
    // Khối mã nếu điều kiện1 true
} else if (điều_kiện2) {
    // Khối mã nếu điều kiện2 true
} else {
    // Khối mã nếu tất cả các điều kiện trên là false
}
```

- **Câu lệnh if lồng nhau**: Bạn có thể đặt một câu lệnh "if" bên trong một câu lệnh "if" khác.

```php
if (điều_kiện1) {
    if (điều_kiện2) {
        // Khối mã nếu điều kiện1 và điều kiện2 đều true
    }
}
```

## Ví dụ
1. **Sử dụng câu lệnh if cơ bản**:
```php
$x = 10;
if ($x > 5) {
    echo "X lớn hơn 5";
}
```

2. **Sử dụng câu lệnh if-else**:
```php
$x = 3;
if ($x > 5) {
    echo "X lớn hơn 5";
} else {
    echo "X không lớn hơn 5";
}
```

3. **Sử dụng câu lệnh if-else if-else**:
```php
$x = 7;
if ($x > 10) {
    echo "X lớn hơn 10";
} else if ($x > 5) {
    echo "X lớn hơn 5 nhưng nhỏ hơn hoặc bằng 10";
} else {
    echo "X nhỏ hơn hoặc bằng 5";
}
```

## Giải thích
- **Cú pháp đúng**: Đảm bảo điều kiện trong dấu ngoặc đơn () và câu lệnh trong dấu ngoặc nhọn {}.
- **Kiểm tra kiểu dữ liệu**: Các điều kiện thường sử dụng toán tử so sánh như `==`, `===`, `!=`, `<`, `>`, `<=`, `>=`.
- **Chạy nhiều câu lệnh**: Bạn có thể chạy nhiều câu lệnh trong khối "if" bằng cách sử dụng dấu chấm phẩy (;) để phân tách chúng.
- **Lưu ý về tính đúng đắn**: Nếu không cẩn thận, việc đặt sai điều kiện có thể dẫn đến lỗi logic trong chương trình.

## Tóm tắt một dòng
Câu lệnh "if" trong PHP là công cụ mạnh mẽ để kiểm tra điều kiện và thực hiện các hành động dựa trên kết quả của điều kiện đó.