<!--
Meta Description: # Clone trong PHP: Hướng Dẫn Chi Tiết và Cách Sử Dụng ## Tóm tắt Clone là một từ khóa trong PHP được sử dụng để tạo ra một bản sao của một đối tượng. ...
Meta Keywords: đối, tượng, một, clone, sao
-->

# Clone trong PHP: Hướng Dẫn Chi Tiết và Cách Sử Dụng

## Tóm tắt
Clone là một từ khóa trong PHP được sử dụng để tạo ra một bản sao của một đối tượng. Bằng cách sử dụng clone, chúng ta có thể sao chép các thuộc tính của đối tượng mà không làm thay đổi đối tượng gốc.

## Tài liệu
Trong PHP, từ khóa `clone` cho phép bạn tạo ra một bản sao của một đối tượng. Điều này rất hữu ích khi bạn cần làm việc với các đối tượng mà không muốn ảnh hưởng đến đối tượng gốc. Khi bạn clone một đối tượng, PHP sẽ tạo ra một bản sao nông (shallow copy) của đối tượng đó. Điều này có nghĩa là các thuộc tính của đối tượng gốc sẽ được sao chép, nhưng nếu bất kỳ thuộc tính nào là một đối tượng khác, bản sao sẽ chỉ tham chiếu đến đối tượng đó, thay vì sao chép nó.

Cú pháp cơ bản để sử dụng `clone` như sau:
```php
$newObject = clone $originalObject;
```

### Chi tiết
- **Mục đích**: Để tạo ra một bản sao của một đối tượng mà không thay đổi đối tượng gốc.
- **Sử dụng**: Dùng trong các trường hợp bạn cần một bản sao độc lập của một đối tượng mà không muốn thay đổi đối tượng gốc.
- **Những điều cần lưu ý**: Khi clone, các thuộc tính đơn giản (như số, chuỗi) sẽ được sao chép, nhưng các thuộc tính là đối tượng khác sẽ chỉ được tham chiếu.

## Ví dụ
### Ví dụ 1: Clone đối tượng đơn giản
```php
class Person {
    public $name;
}

$person1 = new Person();
$person1->name = "John";

$person2 = clone $person1;
$person2->name = "Doe";

echo $person1->name; // Kết quả: John
echo $person2->name; // Kết quả: Doe
```

### Ví dụ 2: Clone với thuộc tính là đối tượng
```php
class Address {
    public $city;
}

class Person {
    public $name;
    public $address;

    public function __construct() {
        $this->address = new Address();
    }
}

$person1 = new Person();
$person1->name = "John";
$person1->address->city = "Hanoi";

$person2 = clone $person1;
$person2->address->city = "Ho Chi Minh City";

echo $person1->address->city; // Kết quả: Ho Chi Minh City
echo $person2->address->city; // Kết quả: Ho Chi Minh City
```

## Giải thích
- **Sao chép nông**: Khi bạn clone một đối tượng, các thuộc tính đơn giản được sao chép nhưng các thuộc tính là đối tượng khác chỉ được tham chiếu, điều này có thể dẫn đến những kết quả không mong muốn nếu bạn không chú ý.
- **Phương thức `__clone()`**: Nếu bạn cần thực hiện các hành động bổ sung khi một đối tượng được clone, bạn có thể định nghĩa phương thức `__clone()` trong lớp của bạn.
- **Cảnh báo**: Tránh sử dụng clone cho các đối tượng có trạng thái phức tạp mà bạn không muốn chia sẻ giữa các bản sao.

## Tóm tắt một dòng
Clone trong PHP cho phép bạn tạo ra một bản sao của một đối tượng mà không làm thay đổi đối tượng gốc, nhưng cần lưu ý rằng các thuộc tính là đối tượng khác chỉ được tham chiếu.