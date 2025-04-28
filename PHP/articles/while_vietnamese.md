<!--
Meta Description: # Câu lệnh "while" trong PHP: Hướng dẫn và Ví dụ ## Tóm tắt Câu lệnh "while" trong PHP là một cấu trúc điều khiển giúp thực hiện một khối lệnh nhiều l...
Meta Keywords: điều, lặp, while, kiện, lệnh
-->

# Câu lệnh "while" trong PHP: Hướng dẫn và Ví dụ

## Tóm tắt
Câu lệnh "while" trong PHP là một cấu trúc điều khiển giúp thực hiện một khối lệnh nhiều lần miễn là điều kiện cho trước là đúng. Đây là một trong những cách cơ bản để xử lý vòng lặp trong lập trình PHP.

## Tài liệu
Câu lệnh "while" được sử dụng để lặp lại một khối mã cho đến khi điều kiện trong biểu thức điều kiện trả về giá trị sai (false). Cú pháp cơ bản của câu lệnh "while" như sau:

```php
while (điều_kiện) {
    // Khối lệnh sẽ được thực hiện nếu điều kiện đúng
}
```

### Mục đích
Mục đích của câu lệnh "while" là để thực hiện các tác vụ lặp đi lặp lại cho đến khi một điều kiện cụ thể không còn đúng. Điều này rất hữu ích trong nhiều trường hợp, chẳng hạn như khi bạn không biết trước số lần cần lặp.

### Cách sử dụng
1. **Khởi tạo biến**: Trước khi sử dụng vòng lặp "while", bạn cần khởi tạo một biến để làm điều kiện.
2. **Cập nhật biến trong vòng lặp**: Phải đảm bảo rằng biến điều kiện sẽ thay đổi trong vòng lặp để tránh rơi vào vòng lặp vô hạn.

## Ví dụ
### Ví dụ 1: Vòng lặp đơn giản

```php
$i = 0;
while ($i < 5) {
    echo "Giá trị của i là: $i\n";
    $i++;
}
```

### Ví dụ 2: Đọc dữ liệu từ mảng

```php
$array = [1, 2, 3, 4, 5];
$i = 0;
while ($i < count($array)) {
    echo "Giá trị trong mảng là: " . $array[$i] . "\n";
    $i++;
}
```

## Giải thích
### Cạm bẫy thường gặp
- **Vòng lặp vô hạn**: Nếu điều kiện không bao giờ trở thành false, vòng lặp sẽ tiếp tục mãi mãi. Ví dụ, nếu bạn quên cập nhật biến điều kiện bên trong vòng lặp, điều này sẽ xảy ra.
  
```php
$i = 0;
while ($i < 5) {
    echo "Giá trị của i là: $i\n"; // Không có $i++
}
```

- **Kiểm tra điều kiện**: Đảm bảo rằng điều kiện trong câu lệnh "while" được kiểm tra đúng cách để tránh kết quả không mong muốn.

### Ghi chú bổ sung
- Sử dụng câu lệnh "while" khi bạn không biết số lần lặp trước. Nếu bạn đã biết số lần lặp, có thể sử dụng câu lệnh "for" thay thế.
- Câu lệnh "while" có thể sử dụng với các điều kiện phức tạp, bao gồm cả các phép so sánh và logic.

## Tóm tắt một dòng
Câu lệnh "while" trong PHP cho phép thực hiện một khối mã nhiều lần cho đến khi điều kiện cho trước không còn đúng.