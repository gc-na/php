<!--
Meta Description: # Từ Khóa "public" trong PHP: Cách Sử Dụng và Ý Nghĩa ## Tóm Tắt "public" trong PHP được sử dụng để xác định mức độ truy cập của các thuộc tính và phư...
Meta Keywords: public, tính, dụng, trong, truy
-->

# Từ Khóa "public" trong PHP: Cách Sử Dụng và Ý Nghĩa

## Tóm Tắt
"public" trong PHP được sử dụng để xác định mức độ truy cập của các thuộc tính và phương thức trong lớp. Đây là một phần quan trọng trong lập trình hướng đối tượng, cho phép lập trình viên kiểm soát khả năng truy cập và bảo vệ dữ liệu.

## Tài Liệu
### Mục Đích
Từ khóa `public` được sử dụng để khai báo rằng một thuộc tính hoặc phương thức trong lớp có thể được truy cập từ bất kỳ đâu trong mã nguồn, bao gồm cả từ các lớp khác và từ bên ngoài lớp.

### Cách Sử Dụng
Khi bạn định nghĩa một thuộc tính hoặc phương thức với từ khóa `public`, bạn mở rộng khả năng truy cập của nó. Cú pháp cơ bản như sau:

```php
class TenLop {
    public $thuocTinh;

    public function phuongThuc() {
        // Nội dung phương thức
    }
}
```

Trong ví dụ trên, `$thuocTinh` và `phuongThuc()` đều có thể được truy cập từ các đối tượng khác.

### Chi Tiết
- **Thuộc tính Public**: Bạn có thể tạo thuộc tính công khai trong lớp để lưu trữ dữ liệu mà bạn muốn cho phép truy cập từ bên ngoài.
- **Phương thức Public**: Các phương thức công khai có thể thực hiện các hành động và trả về kết quả mà người dùng có thể gọi từ các đối tượng của lớp.

## Ví Dụ
Dưới đây là một số ví dụ cơ bản về việc sử dụng từ khóa `public` trong PHP:

### Ví dụ 1: Thuộc tính Public
```php
class HinhChuNhat {
    public $chieuDai;
    public $chieuRong;

    public function __construct($chieuDai, $chieuRong) {
        $this->chieuDai = $chieuDai;
        $this->chieuRong = $chieuRong;
    }
}

$hcn = new HinhChuNhat(10, 5);
echo $hcn->chieuDai; // Kết quả: 10
```

### Ví dụ 2: Phương thức Public
```php
class HinhTron {
    public $banKinh;

    public function __construct($banKinh) {
        $this->banKinh = $banKinh;
    }

    public function tinhDienTich() {
        return pi() * ($this->banKinh ** 2);
    }
}

$ht = new HinhTron(7);
echo $ht->tinhDienTich(); // Kết quả: 153.93804002589985
```

## Giải Thích
Khi sử dụng `public`, bạn cần chú ý đến một số điểm sau:
- **Bảo mật dữ liệu**: Sử dụng thuộc tính công khai có thể dẫn đến việc dữ liệu bị thay đổi từ bên ngoài mà không kiểm soát. Hãy xem xét việc sử dụng `private` hoặc `protected` nếu bạn cần bảo vệ dữ liệu.
- **Truy cập từ bên ngoài**: Nếu bạn không muốn một thuộc tính hoặc phương thức bị truy cập từ bên ngoài, hãy sử dụng các mức độ truy cập khác như `private` hoặc `protected`.
- **Tính đồng nhất**: Nếu một lớp có nhiều thuộc tính và phương thức công khai, hãy đảm bảo rằng chúng có tính nhất quán và dễ hiểu cho người sử dụng.

## Tóm Tắt Một Dòng
Từ khóa `public` trong PHP cho phép truy cập không hạn chế đến các thuộc tính và phương thức của lớp từ bên ngoài, giúp lập trình viên xây dựng ứng dụng hướng đối tượng hiệu quả hơn.