<!--
Meta Description: # PHP 배열 (Array) - PHP 프로그래밍에서의 배열 사용법 ## 개요 PHP에서 배열(array)은 여러 값을 하나의 변수에 저장할 수 있는 데이터 구조입니다. 배열은 데이터의 집합을 효율적으로 관리하고 처리할 수 있는 강력한 도구입니다. 이 문서에서는 PH...
Meta Keywords: php, 배열의, 있습니다, 배열은, fruits
-->

# PHP 배열 (Array) - PHP 프로그래밍에서의 배열 사용법

## 개요
PHP에서 배열(array)은 여러 값을 하나의 변수에 저장할 수 있는 데이터 구조입니다. 배열은 데이터의 집합을 효율적으로 관리하고 처리할 수 있는 강력한 도구입니다. 이 문서에서는 PHP 배열의 사용법, 예제 및 주의사항에 대해 자세히 설명합니다.

## 문서
PHP 배열은 두 가지 주요 유형이 있습니다: 인덱스 배열과 연관 배열. 인덱스 배열은 숫자 인덱스를 사용하여 요소에 접근하고, 연관 배열은 사용자 정의 키를 사용하여 요소에 접근합니다.

### 배열의 목적
배열은 여러 개의 값을 효율적으로 저장하고 처리하기 위해 사용됩니다. 예를 들어, 사용자의 이름 목록, 제품 목록, 설정 값 등을 배열로 관리할 수 있습니다.

### 배열 사용법
PHP에서 배열을 생성하는 방법은 다음과 같습니다:

1. **인덱스 배열 생성**:
   ```php
   $fruits = array("사과", "바나나", "체리");
   ```
   또는 PHP 5.4 이후에는 간단한 구문을 사용할 수 있습니다:
   ```php
   $fruits = ["사과", "바나나", "체리"];
   ```

2. **연관 배열 생성**:
   ```php
   $person = array("이름" => "홍길동", "나이" => 30, "직업" => "개발자");
   ```
   또는:
   ```php
   $person = ["이름" => "홍길동", "나이" => 30, "직업" => "개발자"];
   ```

### 배열의 주요 기능
- 배열의 요소에 접근: `$fruits[0]`는 "사과"를 반환합니다.
- 배열의 길이 확인: `count($fruits)`를 사용하여 배열의 요소 수를 알 수 있습니다.
- 배열 추가: `$fruits[] = "포도";`를 통해 새로운 요소를 추가할 수 있습니다.

## 예제
### 인덱스 배열 예제
```php
$colors = ["빨강", "파랑", "초록"];
echo $colors[1]; // 출력: 파랑
```

### 연관 배열 예제
```php
$car = ["제조사" => "현대", "모델" => "소나타", "연식" => 2022];
echo $car["모델"]; // 출력: 소나타
```

### 배열 반복 처리 예제
```php
foreach ($fruits as $fruit) {
    echo $fruit . " ";
}
// 출력: 사과 바나나 체리
```

## 설명
PHP 배열을 사용할 때 주의해야 할 몇 가지 사항이 있습니다:
- **배열의 인덱스는 0부터 시작**합니다. 따라서 첫 번째 요소의 인덱스는 항상 0입니다.
- **연관 배열은 키를 유일하게 유지**해야 합니다. 동일한 키를 사용하여 추가된 값은 기존 값을 덮어씁니다.
- 배열을 초기화하지 않고 사용하는 경우 "undefined index" 오류가 발생할 수 있습니다.

또한, 배열을 중첩하여 사용할 수 있으며, 다차원 배열을 생성하여 복잡한 데이터 구조를 표현할 수 있습니다.

## 한 줄 요약
PHP 배열은 여러 값을 효율적으로 저장하고 처리할 수 있는 데이터 구조로, 인덱스 배열과 연관 배열의 두 가지 형태로 제공됩니다.