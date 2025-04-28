<!--
Meta Description: # Từ Khóa "extends" Trong PHP: Cách Sử Dụng và Ví Dụ ## Tóm Tắt Từ khóa `extends` trong PHP cho phép một lớp (class) kế thừa các thuộc tính và phương ...
Meta Keywords: lớp, dụng, một, thừa, dog
-->

# Từ Khóa "extends" Trong PHP: Cách Sử Dụng và Ví Dụ

## Tóm Tắt
Từ khóa `extends` trong PHP cho phép một lớp (class) kế thừa các thuộc tính và phương thức từ một lớp khác, hỗ trợ cho việc tổ chức mã nguồn và tái sử dụng mã hiệu quả.

## Tài Liệu
### Mục Đích
Từ khóa `extends` được sử dụng để tạo ra mối quan hệ kế thừa giữa các lớp trong PHP. Kế thừa cho phép một lớp con (subclass) thừa hưởng các thuộc tính và phương thức từ lớp cha (parent class), giúp giảm thiểu mã lặp lại và cải thiện cấu trúc của ứng dụng.

### Cách Sử Dụng
Khi bạn tạo một lớp mới và muốn nó kế thừa từ một lớp có sẵn, bạn sẽ sử dụng cú pháp sau:

```php
class ClassName extends ParentClass {
    // Các thuộc tính và phương thức của lớp con
}
```

### Chi Tiết
- **Lớp Cha (Parent Class)**: Là lớp mà lớp con sẽ kế thừa.
- **Lớp Con (Subclass)**: Là lớp mới được tạo ra, kế thừa từ lớp cha.
- Lớp con có thể sử dụng các phương thức và thuộc tính công khai (public) và bảo vệ (protected) từ lớp cha, nhưng không thể sử dụng thuộc tính riêng tư (private).
- PHP chỉ hỗ trợ kế thừa đơn (một lớp chỉ có thể kế thừa từ một lớp khác).

## Ví Dụ
Dưới đây là một ví dụ đơn giản về việc sử dụng từ khóa `extends`:

```php
class Animal {
    public function speak() {
        return "Animal speaks";
    }
}

class Dog extends Animal {
    public function bark() {
        return "Dog barks";
    }
}

$dog = new Dog();
echo $dog->speak(); // Kết quả: Animal speaks
echo $dog->bark();  // Kết quả: Dog barks
```

Trong ví dụ trên, lớp `Dog` kế thừa từ lớp `Animal`, cho phép nó sử dụng phương thức `speak()` từ lớp cha.

## Giải Thích
Khi sử dụng kế thừa, có một số điều cần lưu ý:
- Nếu lớp con định nghĩa lại một phương thức đã có trong lớp cha, phương thức của lớp con sẽ được gọi, điều này được gọi là "overriding".
- Nếu bạn cần gọi phương thức của lớp cha từ lớp con, bạn có thể sử dụng từ khóa `parent`:

```php
class Dog extends Animal {
    public function speak() {
        return parent::speak() . " and Dog barks";
    }
}
```

- Đảm bảo rằng bạn không tạo ra vòng lặp vô hạn khi kế thừa từ các lớp khác nhau.

## Tóm Tắt Một Dòng
Từ khóa `extends` trong PHP cho phép một lớp kế thừa thuộc tính và phương thức từ một lớp khác, tạo điều kiện cho việc tái sử dụng mã và tổ chức mã hiệu quả.