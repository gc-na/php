<!--
Meta Description: # PHP의 Static 키워드: 클래스와 메모리 관리의 이해 ## 개요 PHP의 `static` 키워드는 클래스 내에서 정적 속성과 메서드를 정의할 때 사용되며, 객체의 인스턴스 없이도 접근할 수 있는 멤버를 생성합니다. 이 기능은 메모리 관리와 성능 최적화를 위해 ...
Meta Keywords: static, 클래스의, 메서드를, 접근할, 인스턴스
-->

# PHP의 Static 키워드: 클래스와 메모리 관리의 이해

## 개요
PHP의 `static` 키워드는 클래스 내에서 정적 속성과 메서드를 정의할 때 사용되며, 객체의 인스턴스 없이도 접근할 수 있는 멤버를 생성합니다. 이 기능은 메모리 관리와 성능 최적화를 위해 유용합니다.

## 문서화

### 목적
`static` 키워드는 클래스의 속성이나 메서드를 정적으로 선언하여, 해당 클래스의 인스턴스를 생성하지 않고도 쉽게 접근할 수 있게 해줍니다. 주로 클래스 레벨의 데이터를 저장하거나, 유틸리티 메서드를 정의할 때 사용됩니다.

### 사용법
- **정적 속성**: 클래스 내에서 `static`으로 선언된 속성은 모든 인스턴스가 공유하며, 클래스 이름을 통해 접근할 수 있습니다.
- **정적 메서드**: `static`으로 선언된 메서드는 인스턴스 없이 호출할 수 있으며, 주로 클래스의 기능을 제공하는 메서드에 사용됩니다.

### 자세한 설명
- 정적 속성 및 메서드는 클래스의 인스턴스와 무관하게 존재하며, 메모리 절약과 성능 향상에 기여합니다.
- `static` 키워드는 클래스의 구조를 더욱 명확하게 할 수 있으며, 코드의 재사용성을 높입니다.
- 정적 메서드 안에서는 정적 속성에 직접 접근할 수 있지만, 인스턴스 속성에는 접근할 수 없습니다. 

## 예제

### 정적 속성 예제
```php
class MyClass {
    public static $staticVar = "Hello, World!";
}

echo MyClass::$staticVar; // 출력: Hello, World!
```

### 정적 메서드 예제
```php
class MyClass {
    public static function staticMethod() {
        return "This is a static method.";
    }
}

echo MyClass::staticMethod(); // 출력: This is a static method.
```

## 설명
- **정적 속성의 초기화**: 정적 속성은 클래스가 로드될 때 초기화되며, 모든 인스턴스에서 공유됩니다. 따라서 값이 변경되면 모든 인스턴스에 영향을 미칩니다.
- **정적 메서드의 접근 제한**: 정적 메서드 내부에서 인스턴스 속성에 접근하려고 하면 오류가 발생합니다. 이 점을 주의해야 합니다.
- **상속과 정적 메서드**: 자식 클래스에서 부모 클래스의 정적 메서드를 호출할 수 있으며, 이는 코드 재사용성을 높여줍니다. 그러나 자식 클래스에서 정적 메서드를 오버라이드하는 것은 권장되지 않습니다.

## 한 줄 요약
PHP에서 `static` 키워드는 클래스의 정적 속성과 메서드를 정의하여 인스턴스 없이도 접근할 수 있는 기능을 제공합니다.