<!--
Meta Description: # Câu lệnh "for" trong PHP: Cách Sử Dụng và Ví Dụ ## Tóm tắt Câu lệnh "for" trong PHP là một cấu trúc điều khiển lặp cho phép lập trình viên thực hiện...
Meta Keywords: lệnh, câu, điều, lặp, một
-->

# Câu lệnh "for" trong PHP: Cách Sử Dụng và Ví Dụ

## Tóm tắt
Câu lệnh "for" trong PHP là một cấu trúc điều khiển lặp cho phép lập trình viên thực hiện một đoạn mã nhiều lần với điều kiện cụ thể.

## Tài liệu
Câu lệnh "for" được sử dụng để lặp qua một khối mã một số lần xác định. Cấu trúc cơ bản của câu lệnh "for" bao gồm ba phần: khởi tạo, điều kiện và cập nhật. Cú pháp của câu lệnh "for" như sau:

```php
for (khởi_tạo; điều_kiện; cập_nhật) {
    // Mã cần lặp
}
```

### Mục đích
Câu lệnh "for" giúp thực hiện một chuỗi lệnh nhiều lần mà không cần phải viết lại mã, giúp tối ưu hóa và giảm thiểu lỗi.

### Sử dụng
- **Khởi tạo**: Thường dùng để khai báo và gán giá trị cho biến đếm.
- **Điều kiện**: Là điều kiện kiểm tra trước khi thực hiện khối mã. Khi điều kiện không còn đúng, vòng lặp sẽ dừng lại.
- **Cập nhật**: Cập nhật giá trị của biến đếm sau mỗi lần lặp.

## Ví dụ
### Ví dụ Cơ Bản
Dưới đây là một ví dụ đơn giản về cách sử dụng câu lệnh "for" trong PHP để in ra các số từ 1 đến 5:

```php
for ($i = 1; $i <= 5; $i++) {
    echo $i . "\n";
}
```

### Ví dụ với Mảng
Câu lệnh "for" cũng có thể được sử dụng để lặp qua các phần tử của mảng:

```php
$fruits = array("Táo", "Chuối", "Cam");
for ($i = 0; $i < count($fruits); $i++) {
    echo $fruits[$i] . "\n";
}
```

## Giải thích
### Các vấn đề phổ biến
- **Quá trình lặp vô hạn**: Nếu điều kiện không bao giờ trở thành sai, vòng lặp sẽ không bao giờ dừng lại, dẫn đến quá tải bộ nhớ hoặc treo ứng dụng. Đảm bảo rằng biến đếm được cập nhật đúng cách.
- **Kiểm tra điều kiện**: Cần chú ý đến thứ tự kiểm tra điều kiện để tránh lỗi logic.
- **Phạm vi biến**: Biến được khởi tạo trong câu lệnh "for" chỉ có phạm vi trong vòng lặp.

## Tóm tắt Một Dòng
Câu lệnh "for" trong PHP là một công cụ mạnh mẽ cho phép lập trình viên thực hiện lặp qua một đoạn mã với điều kiện xác định.