<!--
Meta Description: # Câu lệnh Switch trong PHP: Hướng Dẫn Chi Tiết và Ví Dụ ## Tóm tắt Câu lệnh `switch` trong PHP cho phép lập trình viên thực hiện nhiều lựa chọn dựa t...
Meta Keywords: case, giá, trị, break, thực
-->

# Câu lệnh Switch trong PHP: Hướng Dẫn Chi Tiết và Ví Dụ

## Tóm tắt
Câu lệnh `switch` trong PHP cho phép lập trình viên thực hiện nhiều lựa chọn dựa trên giá trị của một biến, giúp mã nguồn trở nên dễ đọc và bảo trì hơn so với việc sử dụng nhiều câu lệnh `if-else`.

## Tài liệu
### Mục đích
Câu lệnh `switch` được sử dụng để kiểm tra một biến với nhiều giá trị khác nhau và thực hiện các đoạn mã tương ứng với giá trị khớp. Nó rất hữu ích khi bạn cần kiểm tra nhiều điều kiện mà có thể có nhiều trường hợp khác nhau.

### Cú pháp
```php
switch (biến) {
    case giá_trị_1:
        // Mã thực thi cho giá trị 1
        break;
    case giá_trị_2:
        // Mã thực thi cho giá trị 2
        break;
    ...
    default:
        // Mã thực thi nếu không khớp với bất kỳ giá trị nào
}
```

### Chi tiết
- **biến**: biến được kiểm tra giá trị.
- **case giá_trị_i**: mỗi trường hợp kiểm tra một giá trị cụ thể của biến.
- **break**: dùng để thoát khỏi cấu trúc `switch` sau khi thực hiện xong một trường hợp. Nếu không có `break`, PHP sẽ tiếp tục kiểm tra các trường hợp phía dưới.
- **default**: là trường hợp mặc định sẽ được thực thi nếu không có trường hợp nào khớp.

## Ví dụ
### Ví dụ cơ bản
```php
$color = "đỏ";

switch ($color) {
    case "đỏ":
        echo "Màu đỏ được chọn.";
        break;
    case "xanh":
        echo "Màu xanh được chọn.";
        break;
    case "vàng":
        echo "Màu vàng được chọn.";
        break;
    default:
        echo "Không có màu nào được chọn.";
}
```

### Ví dụ sử dụng nhiều giá trị
```php
$day = 5;

switch ($day) {
    case 1:
    case 2:
    case 3:
        echo "Đây là những ngày đầu tuần.";
        break;
    case 4:
    case 5:
        echo "Đây là những ngày giữa tuần.";
        break;
    case 6:
    case 7:
        echo "Đây là cuối tuần.";
        break;
    default:
        echo "Ngày không hợp lệ.";
}
```

## Giải thích
- **Cách sử dụng `break`**: Nếu bạn quên không thêm `break`, PHP sẽ tiếp tục thực hiện tất cả các trường hợp phía dưới, dẫn đến kết quả không như mong đợi.
- **Giá trị so sánh**: `switch` so sánh giá trị của biến bằng phép so sánh bằng (==). Điều này có nghĩa là nếu bạn so sánh giữa số và chuỗi, PHP có thể thực hiện ép kiểu tự động.
- **Trường hợp mặc định**: Mặc dù không bắt buộc, việc sử dụng `default` là rất hữu ích để xử lý các trường hợp không lường trước.

## Tóm tắt một dòng
Câu lệnh `switch` trong PHP cho phép lập trình viên kiểm tra một biến với nhiều giá trị khác nhau và thực hiện mã tương ứng, giúp mã nguồn trở nên rõ ràng hơn.