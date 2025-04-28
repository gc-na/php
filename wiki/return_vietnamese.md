<!--
Meta Description: # Câu lệnh "return" trong PHP: Cách sử dụng và ví dụ ## Tóm tắt Câu lệnh "return" trong PHP được sử dụng để kết thúc một hàm và trả về giá trị cho nơi...
Meta Keywords: return, hàm, câu, lệnh, dụng
-->

# Câu lệnh "return" trong PHP: Cách sử dụng và ví dụ

## Tóm tắt
Câu lệnh "return" trong PHP được sử dụng để kết thúc một hàm và trả về giá trị cho nơi đã gọi hàm đó. Nó là một phần quan trọng giúp lập trình viên có thể xử lý và truyền dữ liệu một cách hiệu quả.

## Tài liệu
### Mục đích
Câu lệnh "return" cho phép bạn gửi một giá trị từ một hàm về nơi mà hàm đó được gọi. Điều này rất hữu ích trong việc xử lý dữ liệu, tính toán và trả về kết quả.

### Cách sử dụng
Câu lệnh "return" có thể được sử dụng trong bất kỳ hàm nào. Cú pháp cơ bản như sau:

```php
function tenHam() {
    // Một số xử lý
    return $giatri; // Trả về giá trị
}
```

Khi hàm được gọi, giá trị được chỉ định sau câu lệnh "return" sẽ được trả về.

### Chi tiết
- Hàm có thể trả về bất kỳ kiểu dữ liệu nào: số, chuỗi, mảng, hoặc đối tượng.
- Nếu không có câu lệnh "return", hàm sẽ tự động trả về giá trị `NULL`.
- Bạn có thể sử dụng nhiều câu lệnh "return" trong một hàm để trả về các giá trị khác nhau trong các tình huống khác nhau.

## Ví dụ
### Ví dụ 1: Hàm đơn giản
```php
function tinhTong($a, $b) {
    return $a + $b;
}

$result = tinhTong(5, 10);
echo $result; // Kết quả: 15
```

### Ví dụ 2: Trả về chuỗi
```php
function chao($ten) {
    return "Xin chào, " . $ten;
}

echo chao("An"); // Kết quả: Xin chào, An
```

### Ví dụ 3: Trả về mảng
```php
function taoMang() {
    return array(1, 2, 3, 4, 5);
}

$mang = taoMang();
print_r($mang); // Kết quả: Array ( [0] => 1 [1] => 2 [2] => 3 [3] => 4 [4] => 5 )
```

## Giải thích
### Các lỗi thường gặp
- **Quên câu lệnh return**: Nếu bạn quên không sử dụng câu lệnh "return" trong một hàm, hàm đó sẽ không trả về giá trị mong muốn, mà sẽ trả về `NULL`.
- **Sử dụng return ở nơi không hợp lệ**: Câu lệnh "return" chỉ có thể được sử dụng bên trong hàm; nếu bạn cố gắng sử dụng nó ở cấp độ toàn cục, nó sẽ gây lỗi.

### Ghi chú bổ sung
- Bạn có thể sử dụng câu lệnh "return" để thoát ra khỏi hàm sớm nếu phát hiện ra một điều kiện không hợp lệ.
- Sử dụng câu lệnh "return" một cách hợp lý giúp mã nguồn của bạn trở nên dễ đọc và dễ bảo trì hơn.

## Tóm tắt một dòng
Câu lệnh "return" trong PHP được sử dụng để kết thúc một hàm và trả về giá trị cho nơi đã gọi hàm đó, giúp xử lý và truyền dữ liệu hiệu quả.