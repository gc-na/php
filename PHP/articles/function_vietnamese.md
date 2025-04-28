<!--
Meta Description: # Hàm trong PHP: Cách sử dụng và ví dụ ## Tóm tắt Hàm trong PHP là một khối mã có thể được gọi nhiều lần trong chương trình, giúp tổ chức và tối ưu hó...
Meta Keywords: hàm, php, trong, dụng, một
-->

# Hàm trong PHP: Cách sử dụng và ví dụ

## Tóm tắt
Hàm trong PHP là một khối mã có thể được gọi nhiều lần trong chương trình, giúp tổ chức và tối ưu hóa mã nguồn, đồng thời cải thiện khả năng tái sử dụng.

## Tài liệu
Hàm trong PHP cho phép lập trình viên định nghĩa một tập hợp các lệnh để thực hiện một nhiệm vụ cụ thể. Việc sử dụng hàm giúp mã nguồn trở nên rõ ràng và dễ bảo trì hơn. 

### Cách định nghĩa hàm
Cú pháp để định nghĩa một hàm trong PHP như sau:

```php
function tenHàm() {
    // Các lệnh thực thi
}
```

### Tham số và giá trị trả về
Hàm có thể nhận tham số và trả về giá trị:

```php
function tinhTong($a, $b) {
    return $a + $b;
}
```

### Gọi hàm
Để gọi hàm, bạn chỉ cần sử dụng tên hàm và truyền tham số (nếu có):

```php
$result = tinhTong(5, 10); // $result sẽ là 15
```

## Ví dụ
Dưới đây là một số ví dụ cơ bản về cách sử dụng hàm trong PHP:

### Ví dụ 1: Hàm không tham số
```php
function chao() {
    echo "Xin chào!";
}
chao(); // Kết quả: Xin chào!
```

### Ví dụ 2: Hàm có tham số
```php
function chaoTen($ten) {
    echo "Xin chào, " . $ten . "!";
}
chaoTen("Nguyễn Văn A"); // Kết quả: Xin chào, Nguyễn Văn A!
```

### Ví dụ 3: Hàm với giá trị trả về
```php
function layTenDayDu($ho, $ten) {
    return $ho . " " . $ten;
}
$tong = layTenDayDu("Nguyễn", "Văn A"); // $tong sẽ là "Nguyễn Văn A"
```

## Giải thích
Khi sử dụng hàm trong PHP, có một số điều cần lưu ý:

1. **Tên hàm**: Tên hàm phải bắt đầu bằng một ký tự hoặc dấu gạch dưới và không được chứa khoảng trắng. PHP phân biệt chữ hoa chữ thường trong tên hàm.
2. **Tham số**: Bạn có thể định nghĩa nhiều tham số cho hàm và cũng có thể sử dụng tham số mặc định.
3. **Phạm vi biến**: Biến được định nghĩa trong hàm chỉ có phạm vi trong hàm đó. Nếu bạn muốn sử dụng biến toàn cục, bạn cần khai báo từ khóa `global`.

## Tóm tắt một dòng
Hàm trong PHP cho phép lập trình viên nhóm các lệnh thành một khối mã có thể tái sử dụng, giúp cải thiện cấu trúc và bảo trì mã nguồn.