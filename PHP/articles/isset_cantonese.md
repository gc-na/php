<!--
Meta Description: # PHP 中的 isset 函数：檢查變量是否存在 ## 簡介 `isset` 是 PHP 中的一個內建函數，用於檢查一個變量是否被設置且其值不為 `NULL`。這個函數在處理表單數據、會話變量或任何需要確認變量存在性的情況下非常有用。 ## 文檔 ### 目的 `isset` 函數的主要目的在於...
Meta Keywords: isset, null, php, var1, var2
-->

# PHP 中的 isset 函数：檢查變量是否存在

## 簡介
`isset` 是 PHP 中的一個內建函數，用於檢查一個變量是否被設置且其值不為 `NULL`。這個函數在處理表單數據、會話變量或任何需要確認變量存在性的情況下非常有用。

## 文檔
### 目的
`isset` 函數的主要目的在於檢查一個或多個變量是否存在且不為 `NULL`。這對於避免未定義變量的錯誤非常重要，特別是在進行條件檢查時。

### 用法
```php
bool isset(mixed $var, mixed ...$vars)
```
- **$var**：要檢查的變量。
- **$vars**：可選的，其他要檢查的變量。

如果所有的變量都存在且不為 `NULL`，`isset` 會返回 `true`；否則返回 `false`。

### 詳細
- 如果變量未被定義，或者其值為 `NULL`，`isset` 將返回 `false`。
- `isset` 可以同時檢查多個變量，只有當所有變量都存在且不為 `NULL` 時，才會返回 `true`。
- 此外，`isset` 不會引發通知錯誤，即使變量未定義。

## 例子
### 基本用法
```php
$var1 = "Hello";
$var2 = null;

if (isset($var1)) {
    echo '$var1 已設置。'; // 這行會被執行
}

if (isset($var2)) {
    echo '$var2 已設置。'; // 這行不會被執行
}
```

### 檢查多個變量
```php
$var1 = "Hello";
$var2 = "World";

if (isset($var1, $var2)) {
    echo '$var1 和 $var2 都已設置。'; // 這行會被執行
}
```

### 在數組中使用
```php
$array = ['key1' => 'value1', 'key2' => null];

if (isset($array['key1'])) {
    echo 'key1 存在且不為 NULL。'; // 這行會被執行
}

if (isset($array['key2'])) {
    echo 'key2 存在且不為 NULL。'; // 這行不會被執行
}
```

## 解釋
- **常見陷阱**：`isset` 只檢查變量是否存在及其值是否為 `NULL`，如果變量的值為 `false`、`0` 或 `""`（空字符串），`isset` 仍會返回 `true`。
- **注意事項**：如果在未定義的變量上使用 `isset`，不會引發錯誤，這使得在檢查變量是否存在時非常安全。
- **性能**：在需要進行多次變量檢查的情況下，`isset` 提供了比 `empty` 或其他類似函數更好的性能。

## 一行總結
`isset` 是一個用於檢查變量是否被設置且不為 `NULL` 的 PHP 內建函數。