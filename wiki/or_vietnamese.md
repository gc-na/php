<!--
Meta Description: # Toán tử "or" trong PHP: Cách sử dụng và ví dụ ## Tóm tắt Toán tử "or" trong PHP là một toán tử logic được sử dụng để kết hợp hai điều kiện. Nếu ít n...
Meta Keywords: trong, toán, một, điều, kiện
-->

# Toán tử "or" trong PHP: Cách sử dụng và ví dụ

## Tóm tắt
Toán tử "or" trong PHP là một toán tử logic được sử dụng để kết hợp hai điều kiện. Nếu ít nhất một trong hai điều kiện là đúng, toàn bộ biểu thức sẽ trả về giá trị đúng (true). Đây là một phần thiết yếu trong lập trình điều kiện, giúp tối ưu hóa các quyết định trong mã nguồn.

## Tài liệu
Toán tử "or" trong PHP là một trong những toán tử logic được sử dụng phổ biến để thực hiện các phép so sánh điều kiện. Nó có thể được sử dụng để kiểm tra nhiều điều kiện trong cùng một câu lệnh. Cú pháp cơ bản của toán tử "or" như sau:

```php
$result = $condition1 or $condition2;
```

Trong đó:
- `$condition1` và `$condition2` là các biểu thức điều kiện có thể đánh giá thành true hoặc false.
- `$result` sẽ nhận giá trị true nếu ít nhất một trong hai điều kiện là true.

### Mục đích
Mục đích của toán tử "or" là để kiểm tra tính đúng sai của các điều kiện khác nhau và thực hiện hành động dựa trên kết quả của phép kiểm tra đó.

### Sử dụng
Toán tử "or" có thể được sử dụng trong các cấu trúc điều kiện như `if`, `while`, và `for`. Nó có thể giúp đơn giản hóa mã nguồn bằng cách giảm số lượng câu lệnh điều kiện cần phải viết.

## Ví dụ
Dưới đây là một số ví dụ cơ bản về cách sử dụng toán tử "or" trong PHP:

### Ví dụ 1: Sử dụng trong câu lệnh if
```php
$a = 5;
$b = 10;

if ($a > 0 or $b > 0) {
    echo "Ít nhất một trong hai biến là dương.";
}
```

### Ví dụ 2: Sử dụng trong vòng lặp
```php
$age = 15;

while ($age < 18 or $age > 60) {
    echo "Bạn không đủ tuổi để tham gia.";
    $age++;
}
```

## Giải thích
Khi sử dụng toán tử "or", cần lưu ý một số điểm sau:
- **Thứ tự ưu tiên**: Toán tử "or" có độ ưu tiên thấp hơn so với toán tử "and". Điều này có thể dẫn đến một số kết quả không như mong muốn nếu không sử dụng dấu ngoặc đúng cách.
- **Hiệu suất**: Trong một số trường hợp, việc sử dụng "or" có thể làm giảm hiệu suất của mã nguồn nếu không được tối ưu hóa đúng cách, nhất là khi có nhiều điều kiện phức tạp.
- **Tránh nhầm lẫn**: Đảm bảo không nhầm lẫn giữa toán tử "or" và toán tử "||". Mặc dù chúng có chức năng tương tự, nhưng "||" có độ ưu tiên cao hơn và có thể dẫn đến các hành vi khác nhau trong một số trường hợp.

## Tóm tắt một dòng
Toán tử "or" trong PHP cho phép kết hợp nhiều điều kiện, trả về true nếu ít nhất một trong các điều kiện là đúng.