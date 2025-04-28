<!--
Meta Description: # PHP에서의 "protected" 키워드: 접근 제어의 이해 ## 개요 PHP에서 "protected" 키워드는 클래스의 속성과 메서드에 대한 접근 제어를 설정하는 데 사용됩니다. 이 키워드는 객체 지향 프로그래밍에서 상속을 관리하는 중요한 역할을 합니다. ## 문...
Meta Keywords: protected, 접근할, 클래스의, name, 속성과
-->

# PHP에서의 "protected" 키워드: 접근 제어의 이해

## 개요
PHP에서 "protected" 키워드는 클래스의 속성과 메서드에 대한 접근 제어를 설정하는 데 사용됩니다. 이 키워드는 객체 지향 프로그래밍에서 상속을 관리하는 중요한 역할을 합니다.

## 문서화
### 목적
"protected"는 클래스 내에서 선언된 속성과 메서드에 대해 접근 권한을 설정합니다. 이 키워드로 선언된 멤버는 해당 클래스와 그 클래스를 상속받은 자식 클래스에서만 접근할 수 있습니다. 이는 객체의 캡슐화와 데이터 보호를 강화합니다.

### 사용법
"protected" 키워드는 클래스 내에서 속성과 메서드를 선언할 때 사용됩니다. 다음은 기본적인 구문입니다:

```php
class ParentClass {
    protected $value;

    protected function displayValue() {
        echo $this->value;
    }
}
```

위의 예제에서 `$value` 속성과 `displayValue` 메서드는 `ParentClass` 내에서만 접근할 수 있으며, 이를 상속받은 자식 클래스에서도 접근 가능합니다.

### 세부사항
- "protected" 멤버는 객체 외부에서는 접근할 수 없습니다. 즉, 인스턴스를 통해 직접 접근할 수 없습니다.
- 자식 클래스에서 부모 클래스의 "protected" 멤버에 접근할 수 있습니다.
- "private"와의 차이점은 "private" 멤버는 해당 클래스 외부에서 접근할 수 없고, 자식 클래스에서도 접근할 수 없습니다.

## 예제
다음은 "protected" 키워드를 사용하는 기본적인 예제입니다:

```php
class Animal {
    protected $name;

    public function __construct($name) {
        $this->name = $name;
    }
}

class Dog extends Animal {
    public function bark() {
        echo $this->name . " says Woof!";
    }
}

$dog = new Dog("Buddy");
$dog->bark(); // 출력: Buddy says Woof!
```

위 예제에서 `Dog` 클래스는 `Animal` 클래스의 "protected" 속성 `$name`에 접근하여 사용할 수 있습니다.

## 설명
"protected" 키워드를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:
- 자식 클래스에서 부모 클래스의 "protected" 멤버에 접근하려고 할 때, 부모 클래스의 인스턴스를 통해 접근할 수 없음을 명심하세요. 반드시 자식 클래스의 인스턴스에서 접근해야 합니다.
- "protected" 멤버는 클래스 내부와 자식 클래스에서만 접근할 수 있으므로, 외부 코드에서 직접 접근하는 경우 오류가 발생합니다.

## 한 줄 요약
"protected"는 PHP 클래스에서 상속받은 클래스에만 접근할 수 있는 속성과 메서드를 정의하는 접근 제어 키워드입니다.