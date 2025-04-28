<!--
Meta Description: # PHP strpos 関数の完全ガイド：文字列内の位置を見つける ## 概要 `strpos` 関数は、PHPにおいて文字列内で特定の文字または文字列が最初に出現する位置を返す非常に便利な関数です。この関数は、文字列操作を行う際に広く使用されており、特に検索やデータ処理に役立ちます。 ## ドキ...
Meta Keywords: strpos, needle, php, hello, position
-->

# PHP strpos 関数の完全ガイド：文字列内の位置を見つける

## 概要
`strpos` 関数は、PHPにおいて文字列内で特定の文字または文字列が最初に出現する位置を返す非常に便利な関数です。この関数は、文字列操作を行う際に広く使用されており、特に検索やデータ処理に役立ちます。

## ドキュメント

### 目的
`strpos` 関数は、指定された文字列内で特定の文字または文字列が最初に現れる位置を探します。返される位置は0から始まるインデックスで、文字列が見つからなかった場合は `false` を返します。

### 使用法
```php
int strpos ( string $haystack , string $needle [, int $offset = 0 ] )
```

- **$haystack**: 検索対象となる文字列。
- **$needle**: 検索する文字または文字列。
- **$offset**: 検索を開始する位置（オプション）。デフォルトは0です。

### 戻り値
- 文字列が見つかった場合：最初の出現位置（0から始まるインデックス）
- 文字列が見つからなかった場合：`false`

## 例

### 基本的な使用例
```php
<?php
$haystack = "Hello, World!";
$needle = "World";
$position = strpos($haystack, $needle);

if ($position !== false) {
    echo "文字列 '$needle' は位置 $position に見つかりました。";
} else {
    echo "文字列 '$needle' は見つかりませんでした。";
}
?>
```

### オフセットを指定した例
```php
<?php
$haystack = "Hello, World! Hello again!";
$needle = "Hello";
$position = strpos($haystack, $needle, 10); // 10文字目から検索

if ($position !== false) {
    echo "2回目の 'Hello' は位置 $position に見つかりました。";
} else {
    echo "文字列 '$needle' は見つかりませんでした。";
}
?>
```

## 説明

### 一般的な落とし穴
- **型の問題**: `strpos` は文字列を返すのではなく、位置を返します。0は「偽」として評価されるため、結果をチェックする際には `!== false` を使用してください。単純に `if ($position)` とすると、位置が0の場合に誤った結果になります。
- **大文字と小文字の区別**: `strpos` は大文字と小文字を区別します。そのため、「hello」と「Hello」は異なる文字列として扱われます。大文字と小文字を区別せずに検索したい場合は、`stripos` 関数を使用してください。

### 追加情報
- `strpos` は非常に効率的で、文字列の長さに関わらず早く検索を行います。
- PHP 7.0以降、`strpos` は `string` 型の引数を受け付けるため、より厳密な型チェックが行われています。

## 一文要約
`strpos` 関数は、PHPで文字列内の特定の文字や文字列の最初の出現位置を見つけるための便利な関数です。