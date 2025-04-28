<!--
Meta Description: # Từ Khóa "const" Trong PHP: Định Nghĩa, Cách Sử Dụng và Ví Dụ ## Tóm Tắt Từ khóa `const` trong PHP được sử dụng để định nghĩa các hằng số, cho phép l...
Meta Keywords: hằng, nghĩa, định, được, const
-->

# Từ Khóa "const" Trong PHP: Định Nghĩa, Cách Sử Dụng và Ví Dụ

## Tóm Tắt
Từ khóa `const` trong PHP được sử dụng để định nghĩa các hằng số, cho phép lưu trữ giá trị không thay đổi trong suốt vòng đời của chương trình. Hằng số được định nghĩa bằng `const` có phạm vi toàn cục và có thể được sử dụng ở bất kỳ đâu trong mã nguồn.

## Tài Liệu
### Mục Đích
Từ khóa `const` cho phép lập trình viên định nghĩa các giá trị hằng không thay đổi, giúp mã nguồn trở nên dễ đọc và bảo trì hơn. Hằng số có thể lưu trữ các giá trị như số nguyên, chuỗi, hoặc bất kỳ loại dữ liệu nào khác.

### Cách Sử Dụng
Để định nghĩa một hằng số bằng `const`, bạn chỉ cần sử dụng cú pháp sau:

```php
const TÊN_HẰNG = GIÁ_TRỊ;
```

- **TÊN_HẰNG**: Tên của hằng số, thường được viết bằng chữ hoa để dễ phân biệt.
- **GIÁ_TRỊ**: Giá trị mà hằng số sẽ lưu trữ.

Lưu ý rằng các hằng số được định nghĩa bằng `const` phải được thiết lập ngay tại thời điểm khai báo và không thể thay đổi sau đó.

### Chi Tiết
- Hằng số được định nghĩa bằng `const` không cần phải sử dụng dấu `$` trước tên hằng.
- Hằng số không thể được thay đổi hoặc xóa sau khi đã được định nghĩa.
- Hằng số không có phạm vi theo đối tượng, điều này có nghĩa là chúng có thể được truy cập từ bất kỳ đâu trong mã nguồn.
- Các hằng số có thể được định nghĩa trong các lớp và sử dụng cú pháp `self::TÊN_HẰNG` để truy cập.

## Ví Dụ
### Ví Dụ Cơ Bản
```php
const PI = 3.14;
const GREETING = "Xin chào";

echo PI; // Kết quả: 3.14
echo GREETING; // Kết quả: Xin chào
```

### Ví Dụ Về Hằng Số Trong Lớp
```php
class Math {
    const E = 2.718;
    
    public function getE() {
        return self::E;
    }
}

$math = new Math();
echo $math->getE(); // Kết quả: 2.718
```

## Giải Thích
- **Cạm Bẫy Thường Gặp**: Một vấn đề phổ biến là cố gắng thay đổi giá trị của hằng số sau khi đã định nghĩa. Điều này sẽ dẫn đến lỗi, vì hằng số không thể thay đổi.
- **Khó Khăn Trong Định Nghĩa**: Hằng số phải được định nghĩa tại cấp độ toàn cục hoặc trong lớp, và không thể nằm trong một hàm.
- **Tính Toán Với Hằng Số**: Hằng số có thể được sử dụng trong các biểu thức toán học, nhưng bạn cần đảm bảo rằng giá trị được định nghĩa chính xác trước khi sử dụng.

## Tóm Tắt Một Dòng
Từ khóa `const` trong PHP cho phép định nghĩa các hằng số không thay đổi, giúp mã nguồn trở nên rõ ràng và dễ bảo trì.