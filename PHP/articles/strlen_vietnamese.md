<!--
Meta Description: # Hàm strlen trong PHP: Tính chiều dài của chuỗi ## Tóm tắt Hàm `strlen` trong PHP được sử dụng để tính toán chiều dài của một chuỗi. Hàm này trả về s...
Meta Keywords: chuỗi, dài, chiều, của, hàm
-->

# Hàm strlen trong PHP: Tính chiều dài của chuỗi

## Tóm tắt
Hàm `strlen` trong PHP được sử dụng để tính toán chiều dài của một chuỗi. Hàm này trả về số lượng ký tự có trong chuỗi, bao gồm cả khoảng trắng và các ký tự đặc biệt.

## Tài liệu
### Mục đích
Hàm `strlen` giúp lập trình viên xác định số lượng ký tự trong một chuỗi. Điều này có thể hữu ích trong nhiều tình huống, chẳng hạn như kiểm tra độ dài của dữ liệu nhập từ người dùng hoặc xử lý chuỗi trong các ứng dụng web.

### Cú pháp
```php
int strlen ( string $string )
```

### Tham số
- `$string`: Chuỗi mà bạn muốn tính chiều dài. Đây là tham số bắt buộc.

### Giá trị trả về
Hàm `strlen` trả về một số nguyên (integer) tương ứng với số lượng ký tự trong chuỗi. Nếu chuỗi rỗng, hàm sẽ trả về 0.

### Ví dụ
```php
// Ví dụ 1: Tính chiều dài của một chuỗi đơn giản
$chuoi1 = "Xin chào, thế giới!";
$doDai1 = strlen($chuoi1);
echo "Chiều dài của chuỗi là: " . $doDai1; // Kết quả: Chiều dài của chuỗi là: 21

// Ví dụ 2: Tính chiều dài của một chuỗi rỗng
$chuoi2 = "";
$doDai2 = strlen($chuoi2);
echo "Chiều dài của chuỗi là: " . $doDai2; // Kết quả: Chiều dài của chuỗi là: 0

// Ví dụ 3: Tính chiều dài của chuỗi có ký tự đặc biệt
$chuoi3 = "PHP & MySQL";
$doDai3 = strlen($chuoi3);
echo "Chiều dài của chuỗi là: " . $doDai3; // Kết quả: Chiều dài của chuỗi là: 12
```

## Giải thích
- **Ký tự UTF-8**: Hàm `strlen` tính toán chiều dài của chuỗi dựa trên số byte. Điều này có thể dẫn đến kết quả không chính xác đối với các ký tự Unicode (như tiếng Việt) vì một số ký tự có thể chiếm nhiều byte. Để tính chiều dài thực sự của chuỗi trong trường hợp này, bạn có thể sử dụng hàm `mb_strlen`.
  
- **Chuỗi rỗng**: Hàm sẽ luôn trả về 0 nếu chuỗi đầu vào là rỗng. Đây là một điều cần lưu ý khi kiểm tra dữ liệu nhập.

- **Không tính toán khoảng trắng**: Hàm `strlen` tính cả khoảng trắng, vì vậy nếu bạn có một chuỗi chỉ chứa khoảng trắng, hàm sẽ trả về chiều dài tương ứng.

## Tóm tắt một dòng
Hàm `strlen` trong PHP được sử dụng để tính chiều dài của chuỗi, trả về số lượng ký tự có trong chuỗi bao gồm cả khoảng trắng và ký tự đặc biệt.