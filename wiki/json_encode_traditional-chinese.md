<!--
Meta Description: # PHP 的 json_encode 函數：轉換數據為 JSON 格式的利器 ## 簡介 `json_encode` 是 PHP 中的一個內建函數，用於將 PHP 數組或對象轉換為 JSON 格式的字符串。這使得在 Web 應用程式中進行數據傳輸時更加方便，因為 JSON 是一種輕量級的數據交換格...
Meta Keywords: json_encode, json, php, false, data
-->

# PHP 的 json_encode 函數：轉換數據為 JSON 格式的利器

## 簡介
`json_encode` 是 PHP 中的一個內建函數，用於將 PHP 數組或對象轉換為 JSON 格式的字符串。這使得在 Web 應用程式中進行數據傳輸時更加方便，因為 JSON 是一種輕量級的數據交換格式，易於人類閱讀和編寫。

## 文檔
### 目的
`json_encode` 函數的主要目的是將 PHP 的數據結構（如數組或對象）轉換成 JSON 格式，這樣可以方便地在前端 JavaScript 中使用或通過 API 傳遞數據。

### 使用方法
```php
string json_encode ( mixed $value [, int $options = 0 [, int $depth = 512 ]] )
```
- **參數**：
  - `$value`：要編碼的 PHP 數據（數組或對象）。
  - `$options`：可選的位掩碼，用於修改編碼行為，常見的選項包括：
    - `JSON_PRETTY_PRINT`：美化輸出，便於閱讀。
    - `JSON_UNESCAPED_UNICODE`：不轉義 Unicode 字符。
  - `$depth`：可選的整數，指定編碼的最大深度，默認為 512。

### 返回值
成功時，返回 JSON 格式的字符串；如果失敗，則返回 `false`。

## 範例
### 基本用法
```php
$data = [
    "name" => "小明",
    "age" => 30,
    "is_student" => false,
    "courses" => ["數學", "物理", "化學"]
];

$json = json_encode($data);
echo $json;  // {"name":"小明","age":30,"is_student":false,"courses":["數學","物理","化學"]}
```

### 使用選項
```php
$data = [
    "name" => "小明",
    "age" => 30,
    "is_student" => false
];

$json = json_encode($data, JSON_PRETTY_PRINT | JSON_UNESCAPED_UNICODE);
echo $json;
// {
//     "name": "小明",
//     "age": 30,
//     "is_student": false
// }
```

## 解釋
在使用 `json_encode` 時，開發人員需要注意以下幾點：

- **非 UTF-8 字符**：`json_encode` 只支持 UTF-8 字符。如果數據中包含其他編碼的字符，將導致編碼失敗，並返回 `false`。
- **循環引用**：如果對象中存在循環引用，`json_encode` 也會失敗。
- **錯誤處理**：可以使用 `json_last_error()` 函數來獲取最近一次操作的錯誤類型，以便於調試。

## 一句總結
`json_encode` 函數是 PHP 中用於將數據結構轉換為 JSON 格式字符串的強大工具，簡化了數據傳輸和存儲過程。