<!--
Meta Description: # PHP 的 foreach 迴圈用法詳解 ## 簡介 `foreach` 是 PHP 中用於遍歷陣列和對象的控制結構。它使得在處理集合時的代碼更加簡潔和易讀，特別是在迴圈中操作每個元素時。 ## 文檔 ### 目的 `foreach` 迴圈旨在簡化對陣列和對象的遍歷過程，讓開發者能夠輕鬆地訪問每...
Meta Keywords: foreach, php, name, value, array
-->

# PHP 的 foreach 迴圈用法詳解

## 簡介
`foreach` 是 PHP 中用於遍歷陣列和對象的控制結構。它使得在處理集合時的代碼更加簡潔和易讀，特別是在迴圈中操作每個元素時。

## 文檔
### 目的
`foreach` 迴圈旨在簡化對陣列和對象的遍歷過程，讓開發者能夠輕鬆地訪問每個元素而無需手動管理索引。

### 用法
`foreach` 的基本語法如下：

```php
foreach ($array as $value) {
    // 代碼邏輯
}
```

在這裡，`$array` 是要遍歷的陣列，`$value` 是當前迴圈中陣列元素的值。

如果需要同時獲取索引及值，可以使用以下語法：

```php
foreach ($array as $key => $value) {
    // 代碼邏輯
}
```

這裡，`$key` 是當前元素的索引，而 `$value` 是當前元素的值。

### 詳細說明
- `foreach` 迴圈可以用於任何一維或多維陣列。
- 對於對象的遍歷，`foreach` 會遍歷對象的公共屬性。
- 在使用 `foreach` 時，陣列的內容可以在迴圈中被修改，但要注意可能會影響迴圈的行為。

## 範例
### 基本用法範例
```php
$fruits = ['蘋果', '香蕉', '橘子'];

foreach ($fruits as $fruit) {
    echo $fruit . "\n";
}
```

### 同時獲取索引和值的範例
```php
$colors = ['red' => '紅色', 'green' => '綠色', 'blue' => '藍色'];

foreach ($colors as $color => $name) {
    echo "$color: $name\n";
}
```

### 多維陣列的範例
```php
$users = [
    ['name' => '小明', 'age' => 25],
    ['name' => '小華', 'age' => 30],
];

foreach ($users as $user) {
    echo "姓名: " . $user['name'] . ", 年齡: " . $user['age'] . "\n";
}
```

## 解釋
- **常見陷阱**：如果在 `foreach` 迴圈中對陣列進行修改，特別是添加或刪除元素，可能會導致未定義的行為。建議在遍歷前做好備份或避免在迴圈中修改原陣列。
- **物件遍歷**：`foreach` 只能遍歷公共屬性，私有屬性將無法訪問。
- **性能注意**：對於大型陣列，`foreach` 的性能通常優於 `for` 迴圈，因為它不需要手動管理索引。

## 一句總結
`foreach` 是 PHP 中一個強大且方便的迴圈結構，用於簡化陣列及對象的遍歷過程。