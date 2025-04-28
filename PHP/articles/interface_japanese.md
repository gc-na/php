<!--
Meta Description: # PHPにおけるインターフェース ## 概要 PHPのインターフェースは、クラスの設計において共通のメソッドシグネチャを定義するための機能です。これにより、異なるクラス間での一貫性を保ちながら、異なる実装を持つことが可能になります。 ## ドキュメント PHPのインターフェースは、キーワード `i...
Meta Keywords: public, function, shape, radius, side
-->

# PHPにおけるインターフェース

## 概要
PHPのインターフェースは、クラスの設計において共通のメソッドシグネチャを定義するための機能です。これにより、異なるクラス間での一貫性を保ちながら、異なる実装を持つことが可能になります。

## ドキュメント
PHPのインターフェースは、キーワード `interface` を使用して定義されます。インターフェースは、メソッドの名前、引数、戻り値の型を指定しますが、メソッドの実装は含まれません。クラスは複数のインターフェースを実装することができ、これにより多重継承のような機能を持つことができます。

### インターフェースの目的
- **抽象化**: インターフェースは、クラス間の共通の契約を定義し、コードの再利用性を高めます。
- **多態性**: 異なるクラスが同じインターフェースを実装することにより、同じメソッドを異なる方法で実行できます。
- **柔軟性**: インターフェースを使用することで、将来的なクラスの変更に柔軟に対応できます。

### 使用法
インターフェースは以下のように定義されます。

```php
interface Animal {
    public function makeSound();
}

class Dog implements Animal {
    public function makeSound() {
        return "ワンワン";
    }
}

class Cat implements Animal {
    public function makeSound() {
        return "ニャー";
    }
}
```

## 例
### 基本的な使用例

以下は、インターフェースを使用した基本的な例です。

```php
interface Shape {
    public function area();
}

class Circle implements Shape {
    private $radius;

    public function __construct($radius) {
        $this->radius = $radius;
    }

    public function area() {
        return pi() * $this->radius ** 2;
    }
}

class Square implements Shape {
    private $side;

    public function __construct($side) {
        $this->side = $side;
    }

    public function area() {
        return $this->side ** 2;
    }
}

$shapes = [new Circle(5), new Square(4)];
foreach ($shapes as $shape) {
    echo $shape->area() . "\n";
}
```

この例では、`Shape`インターフェースを実装する`Circle`と`Square`クラスがあり、それぞれの面積を計算します。

## 説明
### よくある落とし穴
- **メソッドの実装がない**: インターフェースにはメソッドの実装がないため、実装するクラスでは必ず全てのメソッドを実装する必要があります。
- **型の不一致**: インターフェースで定義した型と異なる型を実装しようとするとエラーになります。
- **継承の制限**: PHPではクラスは単一継承ですが、インターフェースは複数実装可能です。これをうまく活用することが重要です。

## 一文の要約
PHPにおけるインターフェースは、クラス間の共通のメソッドシグネチャを定義し、コードの再利用性と柔軟性を高めるための重要な機能です。