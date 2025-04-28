<!--
Meta Description: # Từ Khóa "as" Trong PHP: Tính Năng và Cách Sử Dụng ## Tóm Tắt Từ khóa "as" trong PHP được sử dụng để tạo ra các alias cho các đối tượng hoặc mảng tro...
Meta Keywords: dụng, mảng, trong, các, foreach
-->

# Từ Khóa "as" Trong PHP: Tính Năng và Cách Sử Dụng

## Tóm Tắt
Từ khóa "as" trong PHP được sử dụng để tạo ra các alias cho các đối tượng hoặc mảng trong vòng lặp, giúp mã nguồn trở nên dễ đọc và bảo trì hơn.

## Tài Liệu
Từ khóa "as" là một phần quan trọng trong PHP, thường được sử dụng trong cấu trúc vòng lặp `foreach`. Nó cho phép lập trình viên duyệt qua các phần tử của mảng hoặc đối tượng mà không cần phải chỉ định chỉ số của từng phần tử. Cú pháp của `foreach` kết hợp với "as" giúp làm rõ ràng mục đích của vòng lặp, đồng thời tạo điều kiện cho việc thao tác với các phần tử một cách dễ dàng.

### Cú Pháp
```php
foreach ($mang as $giaTri) {
    // Thực hiện hành động với $giaTri
}
```

### Sử Dụng
- **Duyệt Qua Mảng**: Sử dụng "as" để lấy từng phần tử từ mảng mà không cần biết chỉ số.
- **Duyệt Qua Đối Tượng**: Dùng để lấy các thuộc tính của đối tượng trong các vòng lặp.

## Ví Dụ
```php
// Ví dụ 1: Duyệt qua mảng
$mang = array("Táo", "Chuối", "Cam");
foreach ($mang as $traiCay) {
    echo $traiCay . "\n";
}

// Ví dụ 2: Duyệt qua mảng với khóa
$mangKhóa = array("a" => "Táo", "b" => "Chuối", "c" => "Cam");
foreach ($mangKhóa as $k => $v) {
    echo "Khóa: $k; Giá trị: $v\n";
}
```

## Giải Thích
Khi sử dụng từ khóa "as", có một số điểm cần chú ý:
- **Hiệu suất**: Duyệt qua mảng lớn bằng `foreach` có thể chậm hơn so với sử dụng vòng lặp `for` với chỉ số, nhưng mã sẽ dễ đọc hơn.
- **Tham chiếu**: Có thể sử dụng tham chiếu trong `foreach` để sửa đổi các phần tử gốc của mảng. Cú pháp sử dụng tham chiếu là:
  ```php
  foreach ($mang as &$giaTri) {
      // Thay đổi $giaTri sẽ thay đổi $mang
  }
  unset($giaTri); // Để tránh tham chiếu sai
  ```

## Tóm Tắt Một Dòng
Từ khóa "as" trong PHP giúp lập trình viên duyệt qua các phần tử của mảng và đối tượng một cách dễ dàng, tăng cường khả năng đọc và bảo trì mã nguồn.