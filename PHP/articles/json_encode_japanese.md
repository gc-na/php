<!--
Meta Description: # PHPのjson_encode関数: JSONデータを生成する ## 概要 `json_encode`は、PHPのデータをJSON (JavaScript Object Notation) フォーマットに変換するための関数です。データをAPIレスポンスやWebアプリケーションのデータ交換に使用す...
Meta Keywords: json_encode, data, name, age, json
-->

# PHPのjson_encode関数: JSONデータを生成する

## 概要
`json_encode`は、PHPのデータをJSON (JavaScript Object Notation) フォーマットに変換するための関数です。データをAPIレスポンスやWebアプリケーションのデータ交換に使用する際に非常に便利です。

## ドキュメンテーション
### 機能
`json_encode`関数は、PHPの配列やオブジェクトをJSON形式の文字列に変換します。この関数は、データをクライアントサイドとサーバーサイド間でやり取りする際によく使用されます。

### 使用法
```php
string json_encode(mixed $value[, int $options = 0[, int $depth = 512]]);
```

#### パラメータ
- **$value**: エンコードする配列またはオブジェクト。
- **$options**: エンコードに関するオプションを指定するためのビットマスク。例えば、`JSON_PRETTY_PRINT`を指定すると、整形されたJSONが生成されます。
- **$depth**: JSONエンコードの深さを指定します。デフォルトは512です。

### 戻り値
成功した場合、JSON形式の文字列を返します。失敗した場合は`false`を返します。

## 例
### 基本的な使用例
```php
$data = [
    "name" => "太郎",
    "age" => 25,
    "is_student" => true,
];

$json = json_encode($data);
echo $json; // 出力: {"name":"太郎","age":25,"is_student":true}
```

### オプションを使用した例
```php
$data = [
    "name" => "花子",
    "age" => 22,
    "courses" => ["数学", "科学"]
];

$json = json_encode($data, JSON_PRETTY_PRINT);
echo $json; 
// 出力:
// {
//     "name": "花子",
//     "age": 22,
//     "courses": [
//         "数学",
//         "科学"
//     ]
// }
```

## 説明
`json_encode`を使用する際の一般的な注意点:
- **エンコーディングの失敗**: JSONエンコードが失敗する場合、`json_last_error()`関数を使ってエラーの詳細を確認できます。
- **UTF-8エンコーディング**: `json_encode`はUTF-8エンコーディングされた文字列を処理します。非UTF-8文字列があると、エンコードエラーが発生します。
- **オブジェクトのエンコード**: 公開プロパティを持つオブジェクトのみがエンコードされ、非公開プロパティは無視されます。

## 一文の要約
`json_encode`は、PHPのデータをJSONフォーマットに変換するための強力な関数です。