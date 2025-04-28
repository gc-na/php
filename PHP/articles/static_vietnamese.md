<!--
Meta Description: # Từ Khóa "Static" Trong PHP: Tìm Hiểu Về Tính Năng Quan Trọng ## Tóm Tắt Từ khóa `static` trong PHP được sử dụng để định nghĩa các thuộc tính hoặc ph...
Meta Keywords: tĩnh, tính, thức, phương, thuộc
-->

# Từ Khóa "Static" Trong PHP: Tìm Hiểu Về Tính Năng Quan Trọng

## Tóm Tắt
Từ khóa `static` trong PHP được sử dụng để định nghĩa các thuộc tính hoặc phương thức tĩnh trong lớp, cho phép truy cập mà không cần tạo một đối tượng của lớp đó.

## Tài Liệu
### Mục Đích
Từ khóa `static` cho phép bạn định nghĩa các thuộc tính và phương thức mà không cần phải khởi tạo một đối tượng của lớp. Điều này có nghĩa là bạn có thể truy cập chúng bằng cách sử dụng tên lớp thay vì tên đối tượng.

### Cách Sử Dụng
Khi một thuộc tính hoặc phương thức được khai báo với từ khóa `static`, nó sẽ được chia sẻ giữa tất cả các thể hiện của lớp. Điều này rất hữu ích cho việc lưu trữ dữ liệu chung mà không cần phải khởi tạo lớp nhiều lần.

#### Cách khai báo:
```php
class MyClass {
    public static $staticProperty = 'Giá trị tĩnh';

    public static function staticMethod() {
        return 'Đây là phương thức tĩnh';
    }
}
```

### Truy cập thuộc tính và phương thức tĩnh
Để truy cập thuộc tính và phương thức tĩnh, sử dụng cú pháp `::`:
```php
echo MyClass::$staticProperty; // Xuất: Giá trị tĩnh
echo MyClass::staticMethod();   // Xuất: Đây là phương thức tĩnh
```

### Chi Tiết
- **Khả năng truy cập**: Các thuộc tính và phương thức tĩnh có thể được truy cập từ bên trong hoặc bên ngoài lớp.
- **Không thể sử dụng `$this`**: Bên trong một phương thức tĩnh, không thể sử dụng `$this`, vì không có đối tượng hiện tại nào liên quan.
  
## Ví Dụ
### Ví dụ 1: Khai báo và sử dụng thuộc tính tĩnh
```php
class Counter {
    public static $count = 0;

    public static function increment() {
        self::$count++;
    }
}

Counter::increment();
echo Counter::$count; // Xuất: 1
```

### Ví dụ 2: Khai báo và sử dụng phương thức tĩnh
```php
class Math {
    public static function add($a, $b) {
        return $a + $b;
    }
}

echo Math::add(5, 3); // Xuất: 8
```

## Giải Thích
- **Lỗi phổ biến**: Một số lập trình viên mới có thể nhầm lẫn giữa thuộc tính tĩnh và thuộc tính không tĩnh. Hãy chắc chắn rằng bạn hiểu rõ cách thức hoạt động của chúng.
- **Tính kế thừa**: Các thuộc tính hoặc phương thức tĩnh có thể được kế thừa từ lớp cha, nhưng không thể gọi chúng qua đối tượng của lớp con mà phải sử dụng tên lớp cha hoặc lớp con.

## Tóm Tắt Một Dòng
Từ khóa `static` trong PHP cho phép khai báo thuộc tính và phương thức mà không cần khởi tạo đối tượng, giúp tiết kiệm tài nguyên và quản lý dữ liệu chung hiệu quả.