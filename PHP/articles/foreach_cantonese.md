<!--
Meta Description: # PHP 中的 foreach 迴圈用法詳解 ## 簡介 `foreach` 是 PHP 中用於遍歷陣列的控制結構，能夠簡化陣列元素的訪問和操作。 ## 文檔 `foreach` 迴圈的主要目的是讓開發者能夠輕鬆地遍歷一個陣列或對象的所有元素。這個迴圈語法簡單，易於使用，特別適合處理大型數據集合。...
Meta Keywords: foreach, php, value, array, key
-->

# PHP 中的 foreach 迴圈用法詳解

## 簡介
`foreach` 是 PHP 中用於遍歷陣列的控制結構，能夠簡化陣列元素的訪問和操作。

## 文檔
`foreach` 迴圈的主要目的是讓開發者能夠輕鬆地遍歷一個陣列或對象的所有元素。這個迴圈語法簡單，易於使用，特別適合處理大型數據集合。

### 用法
`foreach` 的基本語法如下：

```php
foreach ($array as $value) {
    // 代碼邏輯
}
```

在這個結構中，`$array` 是要遍歷的陣列，`$value` 代表當前元素。在迴圈中，`$value` 將依次獲取陣列中的每一個元素。

如果需要同時訪問鍵名，可以使用以下語法：

```php
foreach ($array as $key => $value) {
    // 代碼邏輯
}
```

在這裡，`$key` 代表當前元素的鍵名，而 `$value` 仍然是鍵名對應的值。

### 詳細說明
- **可遍歷數據類型**：`foreach` 主要用於陣列和對象。對於陣列，會遍歷每個元素；對於對象，會遍歷每個屬性。
- **性能優勢**：相對於 `for` 迴圈，`foreach` 更加簡潔，並且在處理大數據陣列時性能更佳。
- **引用傳遞**：可以使用引用來遍歷，這樣可以直接修改原始陣列的元素。語法為：

    ```php
    foreach ($array as &$value) {
        // 修改 $value 將影響 $array
    }
    ```

## 範例
以下是一些基本的 `foreach` 用法範例：

### 範例 1：簡單遍歷陣列
```php
$fruits = ['蘋果', '香蕉', '橘子'];
foreach ($fruits as $fruit) {
    echo $fruit . "\n";
}
```

### 範例 2：遍歷關聯陣列
```php
$person = [
    'name' => '小明',
    'age' => 30,
    'city' => '香港'
];
foreach ($person as $key => $value) {
    echo "$key: $value\n";
}
```

### 範例 3：使用引用
```php
$numbers = [1, 2, 3];
foreach ($numbers as &$number) {
    $number *= 2;
}
print_r($numbers); // 輸出：[2, 4, 6]
```

## 解釋
在使用 `foreach` 時，開發者需要注意以下幾點：

- **引用的使用**：當使用引用遍歷陣列時，建議在迴圈結束後將引用變數設為 `null`，以防止意外改變原始數據。
- **空陣列**：如果遍歷的陣列為空，`foreach` 迴圈內的代碼將不會執行。
- **數據類型**：`foreach` 只適用於可遍歷的數據類型，對於其他類型（如整數），將會引發錯誤。

## 一句總結
`foreach` 是 PHP 中用來簡化和高效遍歷陣列及對象的強大控制結構。