<!--
Meta Description: # Sử Dụng Lệnh "foreach" Trong PHP: Hướng Dẫn Chi Tiết và Ví Dụ ## Tóm Tắt Lệnh `foreach` trong PHP là một cấu trúc lặp mạnh mẽ cho phép bạn duyệt qua...
Meta Keywords: foreach, mảng, lệnh, trong, php
-->

# Sử Dụng Lệnh "foreach" Trong PHP: Hướng Dẫn Chi Tiết và Ví Dụ

## Tóm Tắt
Lệnh `foreach` trong PHP là một cấu trúc lặp mạnh mẽ cho phép bạn duyệt qua các phần tử của mảng một cách dễ dàng và hiệu quả.

## Tài Liệu
Lệnh `foreach` được sử dụng để lặp qua các phần tử của mảng mà không cần phải biết kích thước của mảng trước. Nó giúp đơn giản hóa quá trình truy cập từng phần tử và rất hữu ích trong việc xử lý dữ liệu mảng trong các ứng dụng PHP.

### Cú Pháp
Cú pháp cơ bản của lệnh `foreach` như sau:

```php
foreach ($mang as $khoá => $giá_trị) {
    // mã lệnh
}
```

- `$mang`: Mảng mà bạn muốn lặp qua.
- `$khoá`: Tùy chọn, được sử dụng để lưu trữ khóa của phần tử hiện tại.
- `$giá_trị`: Giá trị của phần tử hiện tại.

Bạn cũng có thể sử dụng cú pháp ngắn hơn nếu không cần khóa:

```php
foreach ($mang as $giá_trị) {
    // mã lệnh
}
```

### Mục Đích
Mục đích chính của lệnh `foreach` là để duyệt qua tất cả các phần tử trong một mảng, giúp bạn thực hiện các phép toán hoặc xử lý dữ liệu mà không cần phải quản lý chỉ số.

## Ví Dụ
### Ví dụ 1: Duyệt qua mảng đơn giản
```php
$mang = array("Táo", "Chuối", "Cam");
foreach ($mang as $trái_cây) {
    echo $trái_cây . "\n";
}
```
Kết quả:
```
Táo
Chuối
Cam
```

### Ví dụ 2: Duyệt qua mảng kết hợp
```php
$mang_ket_hop = array("Tên" => "John", "Tuổi" => 30, "Thành phố" => "Hà Nội");
foreach ($mang_ket_hop as $khoá => $giá_trị) {
    echo $khoá . ": " . $giá_trị . "\n";
}
```
Kết quả:
```
Tên: John
Tuổi: 30
Thành phố: Hà Nội
```

## Giải Thích
Khi sử dụng lệnh `foreach`, bạn cần lưu ý một số điều sau:

- **Khóa không nhất thiết phải tồn tại**: Nếu không cần thiết dùng khóa, bạn có thể bỏ qua biến `$khoá`.
- **Giá trị không thay đổi mảng**: Nếu bạn thay đổi giá trị trong vòng lặp, điều đó sẽ không ảnh hưởng đến mảng gốc, trừ khi bạn tham chiếu đến nó.
- **Hiệu suất**: Lệnh `foreach` có hiệu suất tốt hơn trong nhiều trường hợp so với lệnh `for`, đặc biệt là khi làm việc với các mảng lớn.

## Tóm Tắt Một Dòng
Lệnh `foreach` trong PHP là công cụ lý tưởng để duyệt qua các phần tử của mảng một cách dễ dàng và hiệu quả.