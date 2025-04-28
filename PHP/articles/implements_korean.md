<!--
Meta Description: # PHP의 implements 키워드: 인터페이스 구현에 관한 모든 것 ## 개요 `implements`는 PHP에서 클래스가 하나 이상의 인터페이스를 구현할 때 사용하는 키워드입니다. 이를 통해 클래스는 정의된 메서드를 반드시 구현해야 하며, 객체 지향 프로그래밍의...
Meta Keywords: 인터페이스를, public, duck, implements, 합니다
-->

# PHP의 implements 키워드: 인터페이스 구현에 관한 모든 것

## 개요
`implements`는 PHP에서 클래스가 하나 이상의 인터페이스를 구현할 때 사용하는 키워드입니다. 이를 통해 클래스는 정의된 메서드를 반드시 구현해야 하며, 객체 지향 프로그래밍의 다형성을 지원합니다.

## 문서화
`implements` 키워드는 PHP에서 인터페이스를 클래스에 연결하는 역할을 수행합니다. 인터페이스는 메서드의 시그니처(이름, 매개변수, 반환 타입)를 정의하며, 이 인터페이스를 구현하는 클래스는 필수적으로 해당 메서드를 정의해야 합니다. 이를 통해 코드의 일관성과 재사용성을 높일 수 있습니다.

### 사용법
- **인터페이스 정의**: 먼저, 인터페이스를 정의해야 합니다.
- **클래스 구현**: 클래스가 해당 인터페이스를 구현할 때 `implements` 키워드를 사용합니다.

### 세부사항
- 다중 인터페이스 구현: 하나의 클래스는 여러 개의 인터페이스를 동시에 구현할 수 있습니다.
- 메서드 구현: 인터페이스에서 정의된 모든 메서드는 클래스 내에서 반드시 구현해야 하며, 접근 제한자는 `public`이어야 합니다.
- 타입 힌팅: 인터페이스를 타입 힌트로 사용하여 메서드 인자나 반환 타입으로 지정할 수 있습니다.

## 예제
### 기본 사용 예제
```php
interface Animal {
    public function makeSound();
}

class Dog implements Animal {
    public function makeSound() {
        return "Woof!";
    }
}

$dog = new Dog();
echo $dog->makeSound(); // 출력: Woof!
```

### 다중 인터페이스 구현 예제
```php
interface Flyable {
    public function fly();
}

interface Swimmable {
    public function swim();
}

class Duck implements Flyable, Swimmable {
    public function fly() {
        return "Duck is flying!";
    }
    
    public function swim() {
        return "Duck is swimming!";
    }
}

$duck = new Duck();
echo $duck->fly();  // 출력: Duck is flying!
echo $duck->swim(); // 출력: Duck is swimming!
```

## 설명
- **인터페이스 미구현**: 클래스가 인터페이스의 메서드를 구현하지 않으면 `Fatal error`가 발생합니다. 따라서 구현을 잊지 않도록 주의해야 합니다.
- **접근 제한자**: 인터페이스의 메서드는 `public`으로 정의되어야 하며, 그에 따라 클래스에서도 `public`으로 구현해야 합니다. `protected`나 `private`로 구현할 경우 오류가 발생합니다.
- **상속과의 혼동**: `implements`는 인터페이스를 구현하는 것이고, `extends`는 클래스 상속을 나타내므로 두 개념을 혼동하지 않도록 주의해야 합니다.

## 한 문장 요약
PHP의 `implements` 키워드는 클래스가 인터페이스를 구현하여 필수 메서드를 정의하도록 강제하는 키워드입니다.