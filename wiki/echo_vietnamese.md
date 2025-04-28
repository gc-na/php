<!--
Meta Description: # Lệnh `echo` trong PHP: Cách sử dụng và ví dụ ## Tóm tắt Lệnh `echo` trong PHP là một trong những cấu trúc cơ bản nhất, được sử dụng để xuất nội dung...
Meta Keywords: echo, php, một, dụng, xuất
-->

# Lệnh `echo` trong PHP: Cách sử dụng và ví dụ

## Tóm tắt
Lệnh `echo` trong PHP là một trong những cấu trúc cơ bản nhất, được sử dụng để xuất nội dung ra màn hình hoặc gửi dữ liệu tới trình duyệt.

## Tài liệu
Lệnh `echo` là một ngôn ngữ PHP dùng để xuất một hoặc nhiều chuỗi. Nó có thể hiển thị văn bản, biến, hoặc kết quả của các phép toán. Lệnh này không phải là một hàm và không yêu cầu dấu ngoặc đơn để sử dụng.

### Cú pháp cơ bản
```php
echo $string1, $string2, ...;
```

### Các điểm nổi bật
- **Nhiều tham số**: `echo` có thể nhận nhiều tham số, phân cách bằng dấu phẩy.
- **Không trả về giá trị**: `echo` không trả về giá trị nào, vì vậy không thể sử dụng nó trong một biểu thức.
- **Hiệu suất**: `echo` nhanh hơn so với `print`, vì `print` là một hàm và có giá trị trả về.

## Ví dụ

### Ví dụ 1: Xuất một chuỗi đơn giản
```php
echo "Xin chào, thế giới!";
```

### Ví dụ 2: Xuất nhiều chuỗi
```php
$ten = "John";
$tuoi = 30;
echo "Tên tôi là $ten và tôi $tuoi tuổi.";
```

### Ví dụ 3: Xuất kết quả từ phép toán
```php
$a = 5;
$b = 10;
echo "Tổng của $a và $b là: " . ($a + $b);
```

### Ví dụ 4: Xuất HTML
```php
echo "<h1>Chào mừng đến với PHP!</h1>";
```

## Giải thích
Mặc dù `echo` rất dễ sử dụng, người dùng mới thường mắc phải một số lỗi phổ biến:
- **Quên dấu chấm phẩy**: PHP yêu cầu dấu chấm phẩy ở cuối mỗi lệnh, vì vậy việc quên có thể gây ra lỗi cú pháp.
- **Sử dụng dấu ngoặc**: Khi sử dụng `echo`, không cần phải sử dụng dấu ngoặc. Tuy nhiên, nếu bạn muốn sử dụng dấu ngoặc, bạn cần đảm bảo rằng bạn không lẫn lộn với các hàm khác.
- **Biến không được định nghĩa**: Nếu bạn cố gắng xuất một biến mà chưa được định nghĩa, PHP sẽ không gây ra lỗi nhưng sẽ xuất ra giá trị `null`.

## Tóm tắt một dòng
Lệnh `echo` trong PHP là cách đơn giản và hiệu quả để xuất nội dung ra màn hình.