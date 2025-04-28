<!--
Meta Description: # PHP 中的 json_encode 函數詳解：將數據轉換為 JSON 格式 ## 概述 `json_encode` 是 PHP 中一個用於將 PHP 變量轉換為 JSON 格式字符串的內建函數。這個函數通常用於 API 開發及數據傳輸，因為 JSON 格式輕量且易於解析。 ## 文檔 ### ...
Meta Keywords: json_encode, php, json, data, name
-->

# PHP 中的 json_encode 函數詳解：將數據轉換為 JSON 格式

## 概述
`json_encode` 是 PHP 中一個用於將 PHP 變量轉換為 JSON 格式字符串的內建函數。這個函數通常用於 API 開發及數據傳輸，因為 JSON 格式輕量且易於解析。

## 文檔
### 目的
`json_encode` 函數的主要目的是將 PHP 的數組或對象轉換為 JSON 格式，這樣可以方便地在網絡上傳輸數據。

### 使用方法
語法如下：
```php
string json_encode(mixed $value, int $options = 0, int $depth = 512);
```

- **$value**: 要轉換的 PHP 變量（可以是數組或對象）。
- **$options**: 可選參數，指定編碼選項，例如 `JSON_PRETTY_PRINT` 可用於格式化輸出。
- **$depth**: 可選參數，指定編碼時允許的最大嵌套層數，默認為 512。

### 返回值
成功時，`json_encode` 返回一個 JSON 格式的字符串；失敗時返回 `false`。

## 示例
### 基本用法
以下是一個使用 `json_encode` 的簡單例子：
```php
$data = array("name" => "John", "age" => 30, "city" => "Hong Kong");
$jsonData = json_encode($data);
echo $jsonData; // 輸出 {"name":"John","age":30,"city":"Hong Kong"}
```

### 使用選項
使用 JSON 格式化選項：
```php
$data = array("name" => "John", "age" => 30, "city" => "Hong Kong");
$jsonData = json_encode($data, JSON_PRETTY_PRINT);
echo $jsonData;
/*
輸出：
{
    "name": "John",
    "age": 30,
    "city": "Hong Kong"
}
*/
```

## 解釋
### 常見陷阱
1. **無法編碼非 UTF-8 字符**：如果 PHP 變量包含非 UTF-8 字符，`json_encode` 會返回 `false`。這時需要先轉換字符集。
2. **循環引用**：如果對象之間存在循環引用，將導致 `json_encode` 失敗。
3. **空值**：空值（`null`）會被正確編碼，但要確保結構正確。

### 附加說明
- 使用 `json_last_error()` 函數可以檢查 `json_encode` 是否出錯以及錯誤類型。
- `json_encode` 是代碼中處理 API 響應和數據共享的重要工具。

## 總結
`json_encode` 是 PHP 中的強大工具，可將 PHP 數據結構轉換為 JSON 格式，方便數據交換和存儲。