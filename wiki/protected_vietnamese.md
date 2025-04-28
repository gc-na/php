<!--
Meta Description: # Từ Khóa "protected" trong PHP: Cách Sử Dụng và Ý Nghĩa ## Tóm Tắt Từ khóa `protected` trong PHP được sử dụng để xác định quyền truy cập cho các thuộ...
Meta Keywords: lớp, protected, truy, cập, trong
-->

# Từ Khóa "protected" trong PHP: Cách Sử Dụng và Ý Nghĩa

## Tóm Tắt
Từ khóa `protected` trong PHP được sử dụng để xác định quyền truy cập cho các thuộc tính và phương thức của một lớp, cho phép chúng chỉ được truy cập bởi lớp đó và các lớp con của nó.

## Tài Liệu
### Mục Đích
Từ khóa `protected` giúp kiểm soát quyền truy cập của các thuộc tính và phương thức trong lập trình hướng đối tượng (OOP) bằng cách giới hạn khả năng truy cập từ bên ngoài.

### Cách Sử Dụng
Để sử dụng từ khóa `protected`, bạn chỉ cần khai báo nó trước thuộc tính hoặc phương thức trong lớp. Điều này có nghĩa là thuộc tính hoặc phương thức đó chỉ có thể được truy cập từ chính lớp đó hoặc các lớp kế thừa.

### Chi Tiết
- `protected` là một trong ba mức độ truy cập trong PHP, cùng với `public` và `private`.
- Các thuộc tính và phương thức được khai báo là `protected` không thể được truy cập từ bên ngoài lớp hoặc từ các đối tượng không phải là lớp con.
- Nếu một lớp con cần truy cập thuộc tính hoặc phương thức `protected` của lớp cha, nó có thể làm điều này mà không gặp vấn đề gì.

## Ví Dụ
Dưới đây là một ví dụ đơn giản về cách sử dụng từ khóa `protected` trong PHP:

```php
class Cha {
    protected $thuocTinh;

    protected function phuongThuc() {
        return "Đây là phương thức protected.";
    }
}

class Con extends Cha {
    public function layDuLieu() {
        $this->thuocTinh = "Dữ liệu từ lớp con";
        return $this->phuongThuc();
    }
}

$object = new Con();
echo $object->layDuLieu(); // Kết quả: Đây là phương thức protected.
```

## Giải Thích
- Một số người mới học có thể nhầm lẫn giữa `protected` và `private`. Trong khi `private` hạn chế quyền truy cập chỉ trong lớp đó, `protected` cho phép lớp con có thể truy cập.
- Nếu bạn cố gắng truy cập thuộc tính hoặc phương thức `protected` từ một đối tượng không phải là lớp con, PHP sẽ gây ra lỗi.
- Việc sử dụng `protected` giúp bảo vệ dữ liệu của lớp cha nhưng vẫn cho phép các lớp con truy cập và sử dụng nó.

## Tóm Tắt Một Dòng
Từ khóa `protected` trong PHP cho phép các thuộc tính và phương thức của lớp chỉ được truy cập bởi chính lớp và các lớp con của nó, giúp kiểm soát quyền truy cập hiệu quả trong lập trình hướng đối tượng.