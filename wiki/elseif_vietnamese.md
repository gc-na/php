<!--
Meta Description: # Câu lệnh elseif trong PHP: Cách sử dụng và ví dụ ## Tóm tắt Câu lệnh `elseif` trong PHP cho phép lập trình viên kiểm tra nhiều điều kiện trong một c...
Meta Keywords: điều, kiện, elseif, câu, lệnh
-->

# Câu lệnh elseif trong PHP: Cách sử dụng và ví dụ

## Tóm tắt
Câu lệnh `elseif` trong PHP cho phép lập trình viên kiểm tra nhiều điều kiện trong một cấu trúc điều kiện, giúp kiểm soát luồng chương trình một cách linh hoạt và hiệu quả.

## Tài liệu
Câu lệnh `elseif` được sử dụng trong cấu trúc điều kiện `if` để kiểm tra một điều kiện bổ sung nếu điều kiện trước đó không thỏa mãn. Cú pháp cơ bản của câu lệnh này như sau:

```php
if (điều kiện1) {
    // mã thực thi nếu điều kiện1 đúng
} elseif (điều kiện2) {
    // mã thực thi nếu điều kiện2 đúng
} else {
    // mã thực thi nếu không có điều kiện nào đúng
}
```

### Mục đích
Mục đích của `elseif` là cho phép kiểm tra nhiều điều kiện khác nhau mà không cần phải lồng nhiều câu lệnh `if`, giúp mã nguồn trở nên rõ ràng và dễ bảo trì hơn.

### Cách sử dụng
- `elseif` phải đi sau một câu lệnh `if` và trước một câu lệnh `else` (nếu có).
- Bạn có thể sử dụng nhiều câu lệnh `elseif` liên tiếp để kiểm tra nhiều điều kiện khác nhau.

## Ví dụ
### Ví dụ cơ bản
```php
$tuoi = 20;

if ($tuoi < 13) {
    echo "Bạn là trẻ em.";
} elseif ($tuoi < 20) {
    echo "Bạn là thanh thiếu niên.";
} else {
    echo "Bạn là người lớn.";
}
```
Kết quả: `Bạn là người lớn.`

### Ví dụ với nhiều điều kiện
```php
$diem = 85;

if ($diem >= 90) {
    echo "Xuất sắc.";
} elseif ($diem >= 75) {
    echo "Giỏi.";
} elseif ($diem >= 60) {
    echo "Khá.";
} else {
    echo "Trượt.";
}
```
Kết quả: `Giỏi.`

## Giải thích
Khi sử dụng `elseif`, có một số điều cần lưu ý:
- Nếu có nhiều câu lệnh `elseif`, chỉ có một khối mã sẽ được thực thi. Khi một điều kiện đúng, PHP sẽ bỏ qua tất cả các điều kiện còn lại.
- Không nên lạm dụng `elseif` quá nhiều, nếu có nhiều điều kiện, cân nhắc sử dụng cấu trúc `switch` cho rõ ràng hơn.
- Đảm bảo rằng các điều kiện được đặt đúng thứ tự để tránh thiếu sót trong việc kiểm tra.

## Tóm tắt một câu
Câu lệnh `elseif` trong PHP cho phép kiểm tra nhiều điều kiện một cách hiệu quả, giúp tối ưu hóa luồng điều kiện trong mã nguồn.