<!--
Meta Description: # PHP 的 "extends" 關鍵字：繼承與擴展的核心 ## 概述 在 PHP 中，`extends` 關鍵字用於定義類之間的繼承關係，使得一個類可以從另一個類獲取屬性和方法。這一特性促進了代碼的重用性和組織性，是面向對象編程的重要概念。 ## 文檔 ### 目的 `extends` 關鍵字用...
Meta Keywords: extends, php, class, public, function
-->

# PHP 的 "extends" 關鍵字：繼承與擴展的核心

## 概述
在 PHP 中，`extends` 關鍵字用於定義類之間的繼承關係，使得一個類可以從另一個類獲取屬性和方法。這一特性促進了代碼的重用性和組織性，是面向對象編程的重要概念。

## 文檔
### 目的
`extends` 關鍵字用於創建子類，這些子類能夠繼承父類的屬性和方法，從而簡化代碼結構並提高可維護性。

### 使用方式
在 PHP 中，使用 `extends` 來創建一個子類，語法格式如下：

```php
class 子類名 extends 父類名 {
    // 子類的屬性和方法
}
```

### 詳細說明
- **父類**：可以視為基礎類，其內部定義的屬性和方法可以被子類使用。
- **子類**：從父類擴展而來，具備父類的所有功能，並可以添加或重寫方法以滿足特定需求。
- **多重繼承**：PHP 不支持多重繼承，即一個類不能同時繼承多個類。如果需要多重繼承的特性，通常會使用介面（interfaces）來達成。

## 範例
以下是使用 `extends` 的基本範例：

```php
class 動物 {
    public function 吼叫() {
        return "吼！";
    }
}

class 狗 extends 動物 {
    public function 吠叫() {
        return "汪！";
    }
}

$狗 = new 狗();
echo $狗->吼叫(); // 會輸出 "吼！"
echo $狗->吠叫(); // 會輸出 "汪！"
```

在這個範例中，`狗` 類繼承了 `動物` 類的 `吼叫()` 方法，並且自己定義了 `吠叫()` 方法。

## 解釋
### 常見陷阱
- **重寫父類方法**：如果子類中有與父類同名的方法，子類會覆蓋父類的方法。這在不小心時可能導致意外行為。
- **訪問權限**：使用 `protected` 屬性可以讓子類訪問父類的屬性，但 `private` 屬性則無法繼承。
- **抽象類別**：如果父類是抽象類別，那麼子類必須實現所有抽象方法，否則將無法實例化。

## 一句話總結
`extends` 關鍵字在 PHP 中用於定義類的繼承關係，促進代碼的重用與結構化。