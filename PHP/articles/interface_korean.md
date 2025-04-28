<!--
Meta Description: # PHP 인터페이스: 객체 지향 프로그래밍의 핵심 ## 개요 PHP에서 인터페이스는 클래스가 구현해야 하는 메서드의 청사진을 제공하는 구조입니다. 인터페이스는 다형성을 지원하며, 여러 클래스 간의 일관성을 유지하는 데 중요한 역할을 합니다. ## 문서화 인터페이스는 ...
Meta Keywords: public, function, 인터페이스를, 있습니다, 인터페이스는
-->

# PHP 인터페이스: 객체 지향 프로그래밍의 핵심

## 개요
PHP에서 인터페이스는 클래스가 구현해야 하는 메서드의 청사진을 제공하는 구조입니다. 인터페이스는 다형성을 지원하며, 여러 클래스 간의 일관성을 유지하는 데 중요한 역할을 합니다.

## 문서화
인터페이스는 PHP의 객체 지향 프로그래밍(OOP)에서 매우 중요한 개념입니다. 인터페이스는 메서드의 이름과 시그니처(매개변수 및 반환 타입)만 정의하고, 실제 구현은 해당 인터페이스를 구현하는 클래스에서 이루어집니다. 이를 통해 코드의 재사용성과 확장성을 높일 수 있습니다.

### 목적
- **일관성**: 여러 클래스가 동일한 메서드 시그니처를 따르도록 강제합니다.
- **다형성**: 다양한 클래스가 동일한 인터페이스를 구현하여, 같은 방식으로 호출할 수 있습니다.

### 사용법
인터페이스를 정의하려면 `interface` 키워드를 사용합니다. 클래스가 인터페이스를 구현하려면 `implements` 키워드를 사용합니다.

```php
interface Shape {
    public function area();
}

class Rectangle implements Shape {
    private $width;
    private $height;

    public function __construct($width, $height) {
        $this->width = $width;
        $this->height = $height;
    }

    public function area() {
        return $this->width * $this->height;
    }
}
```

## 예제
기본적인 인터페이스 사용 예:

```php
interface Vehicle {
    public function start();
    public function stop();
}

class Car implements Vehicle {
    public function start() {
        echo "차가 시작되었습니다.";
    }
    
    public function stop() {
        echo "차가 멈췄습니다.";
    }
}

$myCar = new Car();
$myCar->start(); // "차가 시작되었습니다."
$myCar->stop();  // "차가 멈췄습니다."
```

## 설명
인터페이스를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:

1. **다중 구현**: PHP는 다중 상속을 지원하지 않지만, 클래스는 여러 인터페이스를 구현할 수 있습니다. 이렇게 하면 다양한 기능을 가진 클래스를 만들 수 있습니다.
   
   ```php
   interface Flyable {
       public function fly();
   }

   interface Swimmable {
       public function swim();
   }

   class Duck implements Flyable, Swimmable {
       public function fly() {
           echo "오리 날기!";
       }

       public function swim() {
           echo "오리 수영!";
       }
   }
   ```

2. **접근 제어**: 인터페이스 내의 모든 메서드는 기본적으로 `public`으로 설정되며, 접근 제어자를 다른 것으로 설정할 수 없습니다.

3. **상수**: 인터페이스에서는 상수를 정의할 수 있으며, 구현하는 클래스에서 이 상수를 사용할 수 있습니다.

## 한줄 요약
PHP의 인터페이스는 클래스가 구현해야 할 메서드의 시그니처를 정의하여 객체 지향 프로그래밍에서 코드의 일관성과 다형성을 지원합니다.