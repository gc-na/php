<!--
Meta Description: # PHP의 instanceof: 객체 타입 확인 방법 ## 개요 `instanceof`는 PHP에서 객체가 특정 클래스 또는 인터페이스의 인스턴스인지 확인하는 데 사용되는 연산자입니다. 이 연산자는 객체 지향 프로그래밍에서 타입 검사를 수행하는 데 유용합니다. ## ...
Meta Keywords: instanceof, 클래스, dog, 객체가, 인터페이스의
-->

# PHP의 instanceof: 객체 타입 확인 방법

## 개요
`instanceof`는 PHP에서 객체가 특정 클래스 또는 인터페이스의 인스턴스인지 확인하는 데 사용되는 연산자입니다. 이 연산자는 객체 지향 프로그래밍에서 타입 검사를 수행하는 데 유용합니다.

## 문서화
`instanceof` 연산자는 특정 객체가 지정된 클래스 또는 인터페이스의 인스턴스인지 확인합니다. 이 연산자는 주로 객체의 타입을 검사하여 유효성을 확인하거나, 특정 클래스 또는 인터페이스에서 제공하는 메소드를 호출할 수 있는지 판단하는 데 사용됩니다.

### 사용법
`instanceof`의 기본 구문은 다음과 같습니다:

```php
$object instanceof ClassName
```

- `$object`: 검사할 객체입니다.
- `ClassName`: 확인할 클래스 또는 인터페이스의 이름입니다.

성공적인 검사는 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.

### 세부사항
- `instanceof`는 클래스의 상속 관계를 고려합니다. 즉, 자식 클래스의 인스턴스는 부모 클래스의 인스턴스로도 간주됩니다.
- 인터페이스의 경우, 객체가 해당 인터페이스를 구현하고 있다면 `true`를 반환합니다.
- PHP 8.0 이상에서는 `mixed` 타입과 함께 사용하여 더욱 유연한 타입 검사를 지원합니다.

## 예제
### 기본 사용 예제
```php
class Animal {}
class Dog extends Animal {}

$dog = new Dog();

if ($dog instanceof Dog) {
    echo "이 객체는 Dog 클래스의 인스턴스입니다.";
}

if ($dog instanceof Animal) {
    echo "이 객체는 Animal 클래스의 인스턴스입니다.";
}
```

### 인터페이스 사용 예제
```php
interface CanFly {}
class Bird implements CanFly {}

$bird = new Bird();

if ($bird instanceof CanFly) {
    echo "이 객체는 CanFly 인터페이스를 구현합니다.";
}
```

## 설명
`instanceof`를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:

- **타입 검사 실패**: 객체가 null일 경우 `instanceof`를 사용할 경우 항상 `false`를 반환합니다. 따라서, null 체크를 선행하는 것이 좋습니다.
- **네임스페이스**: 클래스 이름을 사용할 때는 네임스페이스를 포함해야 할 수 있습니다. 예: `\MyNamespace\MyClass`
- **상속 관계**: 자식 클래스 객체가 부모 클래스 또는 인터페이스로 확인할 수 있지만, 역으로는 확인하지 못합니다.

## 요약 문장
`instanceof`는 PHP에서 객체가 특정 클래스 또는 인터페이스의 인스턴스인지 확인하는 유용한 연산자입니다.