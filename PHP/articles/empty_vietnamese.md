<!--
Meta Description: # Hàm "empty" trong PHP: Kiểm tra Tính Trống của Biến ## Tóm tắt Hàm `empty` trong PHP được sử dụng để kiểm tra xem một biến có chứa giá trị hợp lệ ha...
Meta Keywords: biến, giá, trị, empty, được
-->

# Hàm "empty" trong PHP: Kiểm tra Tính Trống của Biến 

## Tóm tắt
Hàm `empty` trong PHP được sử dụng để kiểm tra xem một biến có chứa giá trị hợp lệ hay không. Nếu biến không có giá trị hoặc có giá trị "trống", hàm sẽ trả về `true`, ngược lại sẽ trả về `false`.

## Tài liệu
### Mục đích
Hàm `empty` rất hữu ích trong việc xác định xem một biến có chứa giá trị hay không trước khi thực hiện các phép toán hoặc xử lý khác. Điều này giúp bảo vệ mã của bạn khỏi lỗi không mong muốn do việc sử dụng các biến chưa được khởi tạo hoặc không có giá trị.

### Cú pháp
```php
empty(mixed $var): bool
```

### Tham số
- **$var**: Biến cần kiểm tra.

### Kết quả
Hàm trả về:
- `true`: Nếu biến không tồn tại, hoặc có giá trị `false`, `0`, `0.0`, `""` (chuỗi rỗng), `"0"` (chuỗi chứa số 0), hoặc `null`.
- `false`: Nếu biến chứa một giá trị hợp lệ khác.

### Chi tiết
- Biến không tồn tại sẽ luôn được coi là "trống".
- Các giá trị `false`, `0`, `""`, và `null` đều bị coi là trống.
- Hàm `empty` không gây ra lỗi khi kiểm tra biến không tồn tại, điều này giúp mã của bạn an toàn hơn.

## Ví dụ
### Ví dụ 1: Kiểm tra biến trống
```php
$var = "";
if (empty($var)) {
    echo "Biến trống!";
}
```
Kết quả: "Biến trống!"

### Ví dụ 2: Kiểm tra biến không tồn tại
```php
if (empty($undefinedVar)) {
    echo "Biến chưa được định nghĩa!";
}
```
Kết quả: "Biến chưa được định nghĩa!"

### Ví dụ 3: Kiểm tra giá trị `0`
```php
$var = 0;
if (empty($var)) {
    echo "Giá trị là 0 nên biến được coi là trống!";
}
```
Kết quả: "Giá trị là 0 nên biến được coi là trống!"

## Giải thích
Một số điểm cần lưu ý khi sử dụng hàm `empty`:
- Hàm `empty` khác với hàm `isset`. Trong khi `isset` chỉ kiểm tra xem biến đã được khởi tạo hay chưa, `empty` kiểm tra cả giá trị của biến.
- Việc sử dụng `empty` có thể giúp bạn tránh được lỗi "Undefined variable" mà bạn có thể gặp phải khi cố gắng sử dụng các biến chưa được định nghĩa.

## Tóm tắt một dòng
Hàm `empty` trong PHP được sử dụng để kiểm tra xem một biến có chứa giá trị hợp lệ hay không, trả về `true` nếu biến trống và `false` nếu có giá trị.