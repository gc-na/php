<!--
Meta Description: # Câu lệnh "break" trong PHP: Hướng dẫn chi tiết và ví dụ ## Tóm tắt Câu lệnh `break` trong PHP được sử dụng để thoát khỏi một vòng lặp hoặc cấu trúc ...
Meta Keywords: break, vòng, lặp, dụng, thoát
-->

# Câu lệnh "break" trong PHP: Hướng dẫn chi tiết và ví dụ

## Tóm tắt
Câu lệnh `break` trong PHP được sử dụng để thoát khỏi một vòng lặp hoặc cấu trúc điều kiện, giúp kiểm soát luồng thực thi của chương trình một cách linh hoạt.

## Tài liệu
Câu lệnh `break` trong PHP cho phép lập trình viên thoát khỏi các vòng lặp như `for`, `foreach`, `while`, và `do...while`. Nó cũng có thể được sử dụng để thoát khỏi các khối `switch`. Mục đích chính của `break` là ngăn cản việc thực hiện tiếp các vòng lặp hoặc câu lệnh điều kiện sau khi đã đạt được một điều kiện nhất định.

### Cú pháp
```php
break [số];
```
Trong đó, `[số]` là số nguyên tùy chọn chỉ định số vòng lặp cần thoát. Nếu không chỉ định, `break` sẽ thoát khỏi vòng lặp gần nhất.

### Ví dụ sử dụng
1. **Sử dụng trong vòng lặp `for`:**
    ```php
    for ($i = 0; $i < 10; $i++) {
        if ($i == 5) {
            break; // Thoát khi $i bằng 5
        }
        echo $i . " ";
    }
    // Kết quả: 0 1 2 3 4
    ```

2. **Sử dụng trong vòng lặp `while`:**
    ```php
    $i = 0;
    while ($i < 10) {
        if ($i == 3) {
            break; // Thoát khi $i bằng 3
        }
        echo $i . " ";
        $i++;
    }
    // Kết quả: 0 1 2
    ```

3. **Sử dụng trong khối `switch`:**
    ```php
    $fruit = "apple";
    switch ($fruit) {
        case "banana":
            echo "This is a banana.";
            break;
        case "apple":
            echo "This is an apple."; // Kết thúc tại đây
            break;
        default:
            echo "Unknown fruit.";
    }
    // Kết quả: This is an apple.
    ```

## Giải thích
Khi sử dụng `break`, lập trình viên cần lưu ý một số điểm sau:

- **Vòng lặp lồng nhau:** Nếu có nhiều vòng lặp lồng nhau, `break` chỉ thoát ra khỏi vòng lặp gần nhất. Để thoát khỏi nhiều vòng lặp, bạn có thể sử dụng `break` với tham số.
  
    ```php
    for ($i = 0; $i < 3; $i++) {
        for ($j = 0; $j < 3; $j++) {
            if ($j == 1) {
                break 2; // Thoát khỏi cả hai vòng lặp
            }
            echo "i = $i, j = $j\n";
        }
    }
    ```

- **Không sử dụng `break` trong các khối không phải vòng lặp:** Nếu sử dụng `break` bên ngoài vòng lặp, PHP sẽ báo lỗi. Đảm bảo rằng `break` chỉ được gọi trong các vòng lặp hoặc khối `switch`.

## Tóm tắt một dòng
Câu lệnh `break` trong PHP được sử dụng để thoát khỏi vòng lặp hoặc khối `switch`, giúp kiểm soát luồng thực thi của chương trình.