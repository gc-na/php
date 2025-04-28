<!--
Meta Description: # PHP의 "or" 연산자: 사용법 및 예제 ## 개요 PHP 프로그래밍 언어에서 "or" 연산자는 논리 연산자로, 두 개의 조건 중 하나라도 참인 경우 참을 반환하는 기능을 제공합니다. 이 연산자는 조건문에서 주로 사용되며, 코드의 가독성을 높이는 데 기여합니다. ...
Meta Keywords: 연산자는, php, result, condition1, condition2
-->

# PHP의 "or" 연산자: 사용법 및 예제

## 개요
PHP 프로그래밍 언어에서 "or" 연산자는 논리 연산자로, 두 개의 조건 중 하나라도 참인 경우 참을 반환하는 기능을 제공합니다. 이 연산자는 조건문에서 주로 사용되며, 코드의 가독성을 높이는 데 기여합니다.

## 문서화
### 목적
"or" 연산자는 두 개의 불리언 (Boolean) 표현식을 결합하여, 둘 중 하나 이상이 참일 경우 전체 표현식이 참으로 평가되도록 합니다. 이는 조건문에서 복잡한 논리를 간단하게 표현할 수 있게 해줍니다.

### 사용법
"or" 연산자는 다음과 같이 사용할 수 있습니다:
```php
$result = $condition1 or $condition2;
```
여기서 `$condition1` 또는 `$condition2`가 참이면 `$result`는 참이 됩니다.

### 세부사항
- "or" 연산자는 낮은 우선 순위를 가지므로, 괄호를 사용하여 명확한 우선 순위를 설정하는 것이 좋습니다. 예를 들어:
  ```php
  $result = $condition1 || ($condition2 or $condition3);
  ```
- "or"는 `||`와 유사하지만, `||`는 더 높은 우선 순위를 가지므로 복잡한 조건을 사용할 때 주의해야 합니다.

## 예제
1. 기본 예제:
```php
$age = 16;
$isAdult = ($age >= 18) or ($age >= 16 && $age < 18);
echo $isAdult; // 출력: 1 (true)
```

2. 여러 조건 사용:
```php
$isMember = false;
$hasCoupon = true;

$discountEligible = $isMember or $hasCoupon;
echo $discountEligible; // 출력: 1 (true)
```

3. 괄호 사용 예제:
```php
$condition1 = false;
$condition2 = false;
$condition3 = true;

$result = ($condition1 or $condition2) or $condition3;
echo $result; // 출력: 1 (true)
```

## 설명
"or" 연산자를 사용할 때는 다음과 같은 함정에 주의해야 합니다:
- "or"와 "||"의 우선 순위 차이로 인해 예상치 못한 결과가 발생할 수 있습니다. 복잡한 조건을 사용할 때는 항상 괄호로 묶어 명확하게 표현하는 것이 중요합니다.
- "or" 연산자는 코드의 가독성을 높일 수 있지만, 너무 많이 사용하면 오히려 읽기 어려운 코드를 만들 수 있으므로 적절한 사용이 필요합니다.

## 한 줄 요약
PHP의 "or" 연산자는 두 조건 중 하나라도 참일 경우 참을 반환하는 논리 연산자입니다.