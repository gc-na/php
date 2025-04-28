<!--
Meta Description: # require_once trong PHP: Cách sử dụng và lợi ích ## Tóm tắt `require_once` là một lệnh trong PHP được sử dụng để bao gồm và thực thi một tập tin PHP ...
Meta Keywords: php, tin, tập, bao, gồm
-->

# require_once trong PHP: Cách sử dụng và lợi ích

## Tóm tắt
`require_once` là một lệnh trong PHP được sử dụng để bao gồm và thực thi một tập tin PHP chỉ một lần trong quá trình thực thi của script. Lệnh này giúp ngăn ngừa lỗi khi tập tin được bao gồm nhiều lần.

## Tài liệu
### Mục đích
Lệnh `require_once` được sử dụng để đảm bảo rằng một tập tin PHP chỉ được bao gồm một lần duy nhất. Nếu tập tin đã được bao gồm trước đó, lệnh này sẽ bỏ qua việc bao gồm đó, giúp tránh các lỗi liên quan đến định nghĩa lại hàm, lớp hoặc biến.

### Cú pháp
```php
require_once 'duong-dan/den-tap-tin.php';
```

### Chi tiết
- **Trả về**: Nếu tập tin được bao gồm thành công, `require_once` sẽ không trả về giá trị nào. Nếu không thể bao gồm tập tin, nó sẽ gây ra một lỗi fatel (lỗi nghiêm trọng).
- **Đường dẫn**: Bạn có thể sử dụng đường dẫn tuyệt đối hoặc tương đối để chỉ định tập tin cần bao gồm.
- **Thời điểm thực thi**: Tập tin được bao gồm sẽ được thực thi ngay khi gặp lệnh `require_once`, do đó, tất cả mã trong tập tin đó sẽ được chạy trong ngữ cảnh của script chính.

## Ví dụ
### Ví dụ 1: Bao gồm tập tin
```php
// file1.php
function hello() {
    echo "Xin chào, thế giới!";
}

// file2.php
require_once 'file1.php';
hello(); // Kết quả: Xin chào, thế giới!
```

### Ví dụ 2: Ngăn ngừa lỗi định nghĩa lại
```php
// file1.php
function hello() {
    echo "Xin chào, thế giới!";
}

// file2.php
require_once 'file1.php';
require_once 'file1.php'; // Không gây lỗi, vì file1.php đã được bao gồm một lần.
hello(); // Kết quả: Xin chào, thế giới!
```

## Giải thích
### Những cạm bẫy thường gặp
- **Lỗi đường dẫn**: Đảm bảo rằng đường dẫn đến tập tin là chính xác. Nếu tập tin không tồn tại, PHP sẽ phát sinh lỗi nghiêm trọng và ngừng thực thi script.
- **Sử dụng `require_once` không đúng cách**: Sử dụng lệnh này cho các tập tin có thể không cần thiết phải bao gồm nhiều lần, như các tập tin chứa biến cấu hình, có thể dẫn đến việc tiêu tốn tài nguyên không cần thiết.
- **Sự khác biệt với `include_once`**: `require_once` sẽ dừng thực thi script khi không thể bao gồm tập tin, trong khi `include_once` sẽ chỉ cảnh báo và tiếp tục thực thi script.

## Tóm tắt một dòng
`require_once` trong PHP là lệnh dùng để bao gồm một tập tin chỉ một lần, giúp tránh lỗi định nghĩa lại và tiết kiệm tài nguyên khi thực thi script.