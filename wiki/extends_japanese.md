<!--
Meta Description: # PHPにおける「extends」キーワードの詳細ガイド ## 概要 PHPの「extends」キーワードは、クラスの継承を実現するために使用されます。この機能により、既存のクラスから新しいクラスを派生させ、コードの再利用や拡張が可能になります。 ## ドキュメンテーション ### 目的 「ext...
Meta Keywords: extends, class, public, function, return
-->

# PHPにおける「extends」キーワードの詳細ガイド

## 概要
PHPの「extends」キーワードは、クラスの継承を実現するために使用されます。この機能により、既存のクラスから新しいクラスを派生させ、コードの再利用や拡張が可能になります。

## ドキュメンテーション
### 目的
「extends」は、あるクラスが別のクラスのプロパティやメソッドを継承する際に使用されます。これにより、親クラスの機能を子クラスで利用できるようになります。

### 使用法
- **基本構文**:
  ```php
  class 親クラス {
      // 親クラスのプロパティやメソッド
  }

  class 子クラス extends 親クラス {
      // 子クラスのプロパティやメソッド
  }
  ```

- **例**:
  ```php
  class Animal {
      public function makeSound() {
          return "Some sound";
      }
  }

  class Dog extends Animal {
      public function makeSound() {
          return "Woof!";
      }
  }

  $dog = new Dog();
  echo $dog->makeSound(); // 出力: Woof!
  ```

### 詳細
- **親クラスと子クラス**: 子クラスは親クラスのすべての公的および保護されたプロパティとメソッドにアクセスできます。
- **メソッドのオーバーライド**: 子クラスで親クラスのメソッドを再定義することができます。これにより、子クラス特有の動作を実装できます。
- **多重継承の不在**: PHPは多重継承をサポートしていませんが、インターフェースを使用することで類似の機能を実現できます。

## 例
### 基本的な使用例
```php
class Vehicle {
    public function start() {
        return "Vehicle is starting";
    }
}

class Car extends Vehicle {
    public function honk() {
        return "Beep!";
    }
}

$car = new Car();
echo $car->start(); // 出力: Vehicle is starting
echo $car->honk();  // 出力: Beep!
```

### メソッドのオーバーライド
```php
class Bird {
    public function fly() {
        return "Flying high!";
    }
}

class Penguin extends Bird {
    public function fly() {
        return "I can't fly!";
    }
}

$penguin = new Penguin();
echo $penguin->fly(); // 出力: I can't fly!
```

## 説明
「extends」を使用する際の一般的な落とし穴や注意点は以下の通りです。

- **アクセス修飾子**: 親クラスのプロパティやメソッドがプライベートの場合、子クラスからはアクセスできません。必要に応じて、プロパティやメソッドを保護または公開に設定することが重要です。
- **コンストラクタの呼び出し**: 子クラスでコンストラクタを定義する場合、親クラスのコンストラクタを呼び出すために `parent::__construct()` を使用することが推奨されます。
- **インターフェースとの併用**: PHPでは、複数のインターフェースを実装することで多重継承のような機能を持たせることができますが、クラスの継承は一つのクラスに限られることを理解しておく必要があります。

## 一文の要約
PHPの「extends」キーワードは、クラスの継承を可能にし、コードの再利用と拡張を促進します。