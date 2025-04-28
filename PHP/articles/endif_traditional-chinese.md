<!--
Meta Description: # PHP 中的 endif：結束條件語句的關鍵字 ## 概述 `endif` 是 PHP 中的一個關鍵字，用於結束使用 `if` 語句的條件判斷。它主要在使用替代語法 (alternative syntax) 時使用，這使得代碼在 HTML 中更加易讀和整潔。 ## 文檔 ### 目的 `endi...
Meta Keywords: php, endif, html, 中嵌入, 必須使用冒號
-->

# PHP 中的 endif：結束條件語句的關鍵字

## 概述
`endif` 是 PHP 中的一個關鍵字，用於結束使用 `if` 語句的條件判斷。它主要在使用替代語法 (alternative syntax) 時使用，這使得代碼在 HTML 中更加易讀和整潔。

## 文檔
### 目的
`endif` 的主要目的是為了結束 `if` 語句，在 PHP 的替代語法中尤為常見。這種語法使得在 HTML 中嵌入 PHP 代碼變得更加直觀。

### 使用方法
在 PHP 中，當使用替代語法時，`if` 語句的結尾必須使用 `endif`。這種用法通常出現在 HTML 代碼中，以下是基本的語法結構：

```php
if (條件):
    // 當條件為真時執行的代碼
endif;
```

### 詳細信息
- `endif` 只能用於替代語法的 `if` 語句中。
- 使用 `endif` 時，必須使用冒號 `:` 開始 `if` 語句，而不是使用大括號 `{}`。
- `endif` 後面不需要跟任何內容，僅用來標示 `if` 語句的結束。

## 範例
以下是一些使用 `endif` 的基本範例：

### 範例 1：簡單的條件判斷
```php
<?php
$score = 85;

if ($score >= 60):
    echo "及格!";
else:
    echo "不及格!";
endif;
?>
```

### 範例 2：在 HTML 中使用
```php
<?php
$user_logged_in = true;
?>

<!DOCTYPE html>
<html>
<head>
    <title>歡迎頁面</title>
</head>
<body>
    <?php if ($user_logged_in): ?>
        <h1>歡迎回來!</h1>
    <?php else: ?>
        <h1>請登錄!</h1>
    <?php endif; ?>
</body>
</html>
```

## 解釋
### 常見陷阱
- **混合語法**：在替代語法中使用大括號 `{}` 來包圍 `if` 語句是錯誤的，必須使用冒號 `:` 開頭並以 `endif` 結束。
- **縮排問題**：在嵌入 HTML 時，注意代碼的縮排，保持清晰的結構可以提高可讀性。
- **條件錯誤**：確保條件語句的邏輯正確，否則可能會導致意外的結果。

## 總結
`endif` 是 PHP 中用於結束替代語法 `if` 語句的重要關鍵字，能夠提升 HTML 中嵌入 PHP 代碼的可讀性和組織性。