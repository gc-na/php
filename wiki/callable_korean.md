<!--
Meta Description: # PHP에서의 호출 가능(callable) 타입: 개념과 사용법 ## 개요 PHP의 `callable`은 함수나 메서드를 동적으로 호출할 수 있도록 해주는 타입이다. 이 타입은 함수 이름, 배열 형태의 객체 메서드, 익명 함수(Closure) 등 다양한 형태로 정의할...
Meta Keywords: callable, 함수나, 메서드를, php, function
-->

# PHP에서의 호출 가능(callable) 타입: 개념과 사용법

## 개요
PHP의 `callable`은 함수나 메서드를 동적으로 호출할 수 있도록 해주는 타입이다. 이 타입은 함수 이름, 배열 형태의 객체 메서드, 익명 함수(Closure) 등 다양한 형태로 정의할 수 있다.

## 문서화
### 목적
`callable`은 PHP에서 함수나 메서드를 변수로 취급할 수 있게 해 주며, 높은 유연성을 제공한다. 이 기능을 통해 코드의 재사용성을 높이고, 동적으로 함수를 호출하여 다양한 상황에 맞게 사용할 수 있다.

### 사용법
`callable` 타입은 PHP의 함수 매개변수, 반환값, 타입 힌트 등에서 사용될 수 있다. 아래는 `callable` 타입을 사용하는 방법의 예시이다.

```php
function executeCallback(callable $callback) {
    return $callback();
}
```

위의 예제에서 `executeCallback` 함수는 `callable` 타입의 매개변수 `$callback`을 받아 실행한다. 호출 가능한 모든 함수나 메서드를 인자로 전달할 수 있다.

### 세부사항
- `callable`은 다음과 같은 형식으로 정의될 수 있다:
  - 문자열 형태의 함수 이름: `'myFunction'`
  - 배열 형태로 클래스의 메서드: `[new MyClass(), 'myMethod']`
  - 익명 함수: `function() { return 'Hello, World!'; }`
- `callable` 타입은 PHP 5.4 이후부터 지원된다.
- `callable`을 사용하여 콜백 함수를 처리할 수 있으며, 이를 통해 이벤트 기반 프로그래밍 및 비동기 처리를 구현할 수 있다.

## 예제
### 예제 1: 문자열 형태의 함수 호출
```php
function greet() {
    return "Hello!";
}

echo executeCallback('greet'); // 출력: Hello!
```

### 예제 2: 배열 형태의 메서드 호출
```php
class Greeter {
    public function greet() {
        return "Hi there!";
    }
}

$greeter = new Greeter();
echo executeCallback([$greeter, 'greet']); // 출력: Hi there!
```

### 예제 3: 익명 함수 호출
```php
$callback = function() {
    return "Hello from Closure!";
};

echo executeCallback($callback); // 출력: Hello from Closure!
```

## 설명
`callable`을 사용할 때 주의할 점은 매개변수로 전달하는 함수나 메서드가 실제로 존재해야 한다는 것이다. 존재하지 않는 함수나 메서드를 호출하려고 하면 `Fatal error`가 발생한다. 또한, `callable`은 타입 힌트에서 사용될 때, 반드시 정의된 형태로 전달되어야 하며, 잘못된 형식으로 전달할 경우 오류가 발생한다.

## 한 줄 요약
PHP에서 `callable`은 함수나 메서드를 동적으로 호출할 수 있도록 해주는 타입으로, 다양한 형태로 정의할 수 있다.