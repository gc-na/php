<!--
Meta Description: # PHP中的常量（const）用法詳解 ## 概述 在PHP中，`const`關鍵字用來定義類別常量，這些常量是在類別中聲明並且不能被修改的值。使用`const`可以幫助開發者在程式中保持數據的穩定性和一致性。 ## 文檔 ### 目的 `const`的主要目的是在類別內部定義不會改變的值。與普通...
Meta Keywords: const, circle, 在php中, php, class
-->

# PHP中的常量（const）用法詳解

## 概述
在PHP中，`const`關鍵字用來定義類別常量，這些常量是在類別中聲明並且不能被修改的值。使用`const`可以幫助開發者在程式中保持數據的穩定性和一致性。

## 文檔
### 目的
`const`的主要目的是在類別內部定義不會改變的值。與普通變數不同，常量在定義後無法重新賦值，這使得它們特別適合用於定義不會變動的設置或參數。

### 用法
在PHP中，使用`const`來定義常量的基本語法如下：
```php
class ClassName {
    const CONSTANT_NAME = '常量值';
}
```
常量的名稱必須遵循標識符的命名規則，且通常使用全大寫字母以便於識別。

### 詳細說明
- **可訪問性**：常量可以通過`ClassName::CONSTANT_NAME`的方式來訪問。
- **作用範圍**：常量的作用範圍僅限於定義它的類別，不可以在類別外部直接訪問。
- **靜態性**：常量是靜態的，這意味著它們不需要實例化類別來訪問。

## 範例
下面是一些基本的用法範例：

### 範例1：定義和訪問常量
```php
class MyClass {
    const MY_CONSTANT = 'Hello, World!';
}

echo MyClass::MY_CONSTANT; // 輸出：Hello, World!
```

### 範例2：在類別內部使用常量
```php
class Circle {
    const PI = 3.14;

    public function area($radius) {
        return self::PI * $radius * $radius;
    }
}

$circle = new Circle();
echo $circle->area(5); // 輸出：78.5
```

## 解釋
### 常見問題及注意事項
- **不可修改**：一旦定義後，常量的值無法修改，這就意味著在類別內部不能使用賦值操作來改變它。
- **命名規範**：常量的名稱應遵循全大寫字母的慣例，以便於與變數區分。
- **使用static關鍵字**：雖然常量是靜態的，但它們不需要`static`關鍵字來聲明，因為`const`本身已經隱含了靜態的性質。

## 總結
在PHP中，`const`關鍵字用來創建類別常量，這些常量在定義後無法被修改，並且是靜態的，適合用於定義不變的值。