<!--
Meta Description: # Lớp trong PHP: Tìm Hiểu Về Khái Niệm và Cách Sử Dụng ## Tóm tắt Lớp (Class) trong PHP là một cấu trúc quan trọng trong lập trình hướng đối tượng, ch...
Meta Keywords: lớp, php, một, trong, đối
-->

# Lớp trong PHP: Tìm Hiểu Về Khái Niệm và Cách Sử Dụng

## Tóm tắt
Lớp (Class) trong PHP là một cấu trúc quan trọng trong lập trình hướng đối tượng, cho phép lập trình viên định nghĩa các đối tượng với các thuộc tính và phương thức riêng.

## Tài liệu
Lớp trong PHP được sử dụng để tạo ra các đối tượng. Lớp là một bản thiết kế cho đối tượng, cung cấp cách để tổ chức mã, làm cho nó dễ đọc và bảo trì hơn. Một lớp có thể chứa các thuộc tính (biến) và phương thức (hàm) mà các đối tượng của lớp đó có thể sử dụng. 

### Cấu trúc của một lớp
Một lớp trong PHP được định nghĩa bằng từ khóa `class`, theo cú pháp sau:

```php
class TênLớp {
    // Thuộc tính
    public $thuocTinh;

    // Phương thức
    public function tenPhuongThuc() {
        // Mã thực hiện
    }
}
```

### Tạo đối tượng
Để tạo một đối tượng từ lớp, bạn sử dụng từ khóa `new`:

```php
$doiTuong = new TênLớp();
```

### Kế thừa
PHP hỗ trợ kế thừa, cho phép một lớp kế thừa thuộc tính và phương thức từ lớp cha:

```php
class LopCha {
    public function phuongThucCha() {
        // Mã thực hiện
    }
}

class LopCon extends LopCha {
    public function phuongThucCon() {
        // Mã thực hiện
    }
}
```

## Ví dụ
Dưới đây là một ví dụ đơn giản về cách định nghĩa và sử dụng lớp trong PHP:

```php
class Xe {
    public $mau;
    public $hang;

    public function __construct($mau, $hang) {
        $this->mau = $mau;
        $this->hang = $hang;
    }

    public function thongTin() {
        return "Xe màu {$this->mau} và hãng {$this->hang}.";
    }
}

$xe1 = new Xe("Đỏ", "Toyota");
echo $xe1->thongTin(); // Xuất: Xe màu Đỏ và hãng Toyota.
```

## Giải thích
Khi làm việc với lớp trong PHP, có một số điều cần lưu ý:
- **Tính chất truy cập**: PHP hỗ trợ ba loại tính chất truy cập - `public`, `protected`, và `private`. Bạn cần chọn loại phù hợp để bảo vệ dữ liệu của lớp.
- **Từ khóa `this`**: Khi truy cập thuộc tính hoặc phương thức của lớp trong một phương thức, bạn cần sử dụng từ khóa `this`.
- **Kế thừa**: Đảm bảo rằng lớp con không thay đổi hành vi của lớp cha một cách không mong muốn, điều này có thể dẫn đến lỗi khó hiểu.

## Tóm tắt một dòng
Lớp trong PHP là một cấu trúc lập trình hướng đối tượng cho phép định nghĩa các đối tượng với thuộc tính và phương thức riêng biệt.