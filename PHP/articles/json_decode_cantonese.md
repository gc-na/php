<!--
Meta Description: # PHP 的 json_decode 函數詳解及用法 ## 簡介 `json_decode` 是 PHP 中用來將 JSON 格式的字符串轉換成 PHP 變量的函數。這個功能在處理 API 回應或存儲 JSON 數據時非常有用。 ## 文檔 `json_decode` 函數的主要目的是將 JSON...
Meta Keywords: php, json, json_decode, jsonstring, name
-->

# PHP 的 json_decode 函數詳解及用法

## 簡介
`json_decode` 是 PHP 中用來將 JSON 格式的字符串轉換成 PHP 變量的函數。這個功能在處理 API 回應或存儲 JSON 數據時非常有用。

## 文檔
`json_decode` 函數的主要目的是將 JSON 字符串解碼為 PHP 變量。這可以是一個對象或數組，具體取決於函數的參數設定。

### 用法
```php
mixed json_decode ( string $json [, bool $assoc = false [, int $depth = 512 [, int $options = 0 ]]] )
```

### 參數
- **$json**: 必需，待解碼的 JSON 字符串。
- **$assoc**: 可選，當設置為 `true` 時，返回關聯數組；若為 `false`（預設值），則返回對象。
- **$depth**: 可選，指定解碼時的最大深度，預設為 512。
- **$options**: 可選，指定額外的選項，預設為 0。

### 返回值
返回解碼後的 PHP 變量，如果出現錯誤則返回 `null`。

### 錯誤處理
如 JSON 字符串無效，`json_decode` 會返回 `null`，可以使用 `json_last_error()` 函數來檢查錯誤類型。

## 範例
### 基本用法示例
```php
$jsonString = '{"name": "John", "age": 30}';
$decoded = json_decode($jsonString);
echo $decoded->name; // 輸出: John
```

### 返回關聯數組
```php
$jsonString = '{"name": "John", "age": 30}';
$decodedArray = json_decode($jsonString, true);
echo $decodedArray['name']; // 輸出: John
```

### 錯誤處理示例
```php
$jsonString = '{"name": "John", "age": }'; // 無效 JSON
$decoded = json_decode($jsonString);

if (is_null($decoded)) {
    echo '錯誤: ' . json_last_error_msg(); // 輸出錯誤訊息
}
```

## 解釋
在使用 `json_decode` 時，開發者應留意以下幾點：
- 確保傳遞的 JSON 字符串是有效的，否則將返回 `null`。
- 當使用 `assoc` 參數為 `true` 時，會返回關聯數組，這可能改變你對數據結構的預期。
- 大多數情況下，JSON 的鍵是區分大小寫的，因此在訪問對象屬性或數組鍵時需小心。
- 使用 `json_last_error()` 可以幫助識別和排除錯誤。

## 一句總結
`json_decode` 是 PHP 中將 JSON 字符串轉換為 PHP 變量的強大工具，廣泛應用於數據處理和 API 整合中。