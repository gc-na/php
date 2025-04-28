<!--
Meta Description: # PHPにおける「protected」修飾子の徹底解説 ## 概要 PHPの「protected」修飾子は、クラスのプロパティやメソッドに対するアクセス制御を提供します。この修飾子を使用することで、クラス内部とそのサブクラスからのアクセスを許可し、外部からはアクセスできないように制御します。 ##...
Meta Keywords: protected, function, class, 修飾子は, public
-->

# PHPにおける「protected」修飾子の徹底解説

## 概要
PHPの「protected」修飾子は、クラスのプロパティやメソッドに対するアクセス制御を提供します。この修飾子を使用することで、クラス内部とそのサブクラスからのアクセスを許可し、外部からはアクセスできないように制御します。

## ドキュメンテーション
「protected」は、クラスのプロパティやメソッドに適用されるアクセス修飾子の一つです。これを使用することで、オブジェクト指向プログラミングにおけるカプセル化を実現し、クラスの内部実装を隠蔽することができます。

### 目的
- クラスのプロパティやメソッドのアクセスを制限し、クラスの外部からの不正なアクセスを防ぐ。
- サブクラスからのアクセスを許可し、継承を利用したコードの再利用を促進する。

### 使用法
「protected」修飾子は、以下のようにクラス内でプロパティやメソッドを宣言する際に使用します。

```php
class ParentClass {
    protected $protectedProperty;

    protected function protectedMethod() {
        // メソッドの内容
    }
}

class ChildClass extends ParentClass {
    public function accessProtected() {
        $this->protectedProperty = 'アクセス成功';
        $this->protectedMethod();
    }
}
```

## 例
以下に「protected」を使用した基本的な例を示します。

```php
class Base {
    protected $value;

    protected function displayValue() {
        return $this->value;
    }
}

class Derived extends Base {
    public function setValue($val) {
        $this->value = $val;
    }

    public function showValue() {
        return $this->displayValue();
    }
}

$instance = new Derived();
$instance->setValue(10);
echo $instance->showValue(); // 出力: 10
```

## 説明
「protected」を使用する際の一般的な注意点や落とし穴には以下のようなものがあります：

- **外部アクセス不可**: 「protected」プロパティやメソッドは、クラスの外部からは直接アクセスできません。したがって、外部からアクセスする必要がある場合は、publicメソッドを用意する必要があります。
- **サブクラスでのオーバーライド**: サブクラスで「protected」メソッドをオーバーライドすることができますが、メソッドのシグネチャは一致させる必要があります。
- **継承関係の理解**: 継承が適切に行われていない場合、「protected」プロパティやメソッドにアクセスできず、エラーが発生することがあります。

## 一文要約
PHPの「protected」修飾子は、クラス内部およびそのサブクラスからのアクセスを許可し、外部からのアクセスを制限するためのアクセス制御機能です。