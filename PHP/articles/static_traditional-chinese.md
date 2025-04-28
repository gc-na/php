<!--
Meta Description: # PHP 中的靜態 (Static) 關鍵字：深入解析與使用指南 ## 簡介 在 PHP 中，`static` 關鍵字用於定義靜態屬性和靜態方法，這使得這些屬性和方法可以在不創建類實例的情況下進行訪問。靜態成員屬於類而不是類的實例，這意味著它們可以被所有對該類的實例共享。 ## 文檔 ### 目的...
Meta Keywords: static, php, public, counter, myclass
-->

# PHP 中的靜態 (Static) 關鍵字：深入解析與使用指南

## 簡介
在 PHP 中，`static` 關鍵字用於定義靜態屬性和靜態方法，這使得這些屬性和方法可以在不創建類實例的情況下進行訪問。靜態成員屬於類而不是類的實例，這意味著它們可以被所有對該類的實例共享。

## 文檔
### 目的
`static` 關鍵字的主要目的是允許在類中定義屬性和方法，這些屬性和方法不依賴於類的具體實例。這對於需要共享數據或行為的情況非常有用。

### 用法
在 PHP 中，使用 `static` 關鍵字可以這樣定義靜態屬性和靜態方法：

1. **靜態屬性**：靜態屬性在類被加載時初始化，並且在所有對該類的實例之間共享。
2. **靜態方法**：靜態方法可以直接通過類名調用，而無需創建該類的實例。

靜態成員的語法如下：
```php
class MyClass {
    public static $myStaticProperty;

    public static function myStaticMethod() {
        // 方法實現
    }
}
```

要訪問靜態屬性或方法，可以使用以下語法：
```php
MyClass::$myStaticProperty;
MyClass::myStaticMethod();
```

## 範例
以下是靜態屬性和靜態方法的基本用法示例：

```php
class Counter {
    public static $count = 0;

    public static function increment() {
        self::$count++;
    }
}

// 使用靜態方法增長計數
Counter::increment();
Counter::increment();

echo Counter::$count; // 輸出 2
```

## 解釋
### 常見陷阱與注意事項
1. **訪問靜態屬性**：靜態屬性可以通過 `self::` 或 `ClassName::` 來訪問，使用 `$this->` 是不正確的，因為 `$this` 代表實例。
2. **靜態方法中的上下文**：在靜態方法內部，使用 `self` 來引用靜態屬性和其他靜態方法，而不能使用 `$this`。
3. **靜態 vs. 實例成員**：靜態成員的數據是共享的，而每個實例的實例成員是獨立的。這意味著如果一個靜態屬性被修改，所有實例都會看到這一變化。

### 額外備註
靜態方法無法訪問非靜態屬性和方法，這是因為非靜態成員只在實例上下文中存在。因此，在設計類時要仔細考慮成員的靜態或實例性質。

## 一句總結
在 PHP 中，`static` 關鍵字用於定義共享的靜態屬性和方法，這些成員可以在不創建類實例的情況下直接通過類名訪問。