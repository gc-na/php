<!--
Meta Description: # PHP의 기본값 (default) 이해하기 ## 개요 PHP에서 'default'는 조건문, 스위치 문 등 다양한 맥락에서 사용되며, 특정 상황에서 기본적으로 실행되는 코드를 정의할 때 사용됩니다. 이 기능은 프로그램의 흐름을 제어하고 예외 상황을 처리하는 데 유용...
Meta Keywords: default, switch, case, break, echo
-->

# PHP의 기본값 (default) 이해하기

## 개요
PHP에서 'default'는 조건문, 스위치 문 등 다양한 맥락에서 사용되며, 특정 상황에서 기본적으로 실행되는 코드를 정의할 때 사용됩니다. 이 기능은 프로그램의 흐름을 제어하고 예외 상황을 처리하는 데 유용합니다.

## 문서화

### 목적
'Default' 키워드는 PHP의 switch 문에서 사용되며, 주어진 조건에 맞는 case가 없을 때 실행되는 코드 블록을 정의합니다. 이를 통해 프로그래머는 예상치 못한 입력에 대한 처리를 쉽게 할 수 있습니다.

### 사용법
PHP의 switch 문 내에서 default는 선택 사항이며, switch 문이 특정 case에 맞지 않을 때 실행할 코드를 지정합니다. 다음은 기본적인 문법입니다:

```php
switch (식) {
    case 값1:
        // 코드 블록 1
        break;
    case 값2:
        // 코드 블록 2
        break;
    default:
        // 기본 코드 블록
}
```

### 세부사항
- `switch` 문은 주어진 표현식의 값을 비교하여 해당하는 case 문을 찾습니다.
- `case` 문이 일치하면 그 코드 블록이 실행되고, `break` 문을 만나면 switch 문을 종료합니다.
- 만약 어떤 `case`도 일치하지 않으면 `default` 블록이 실행됩니다.
- `default`는 switch 문 내에서 마지막에 위치하는 것이 일반적입니다.

## 예제

### 기본 예제
다음은 'default' 키워드를 사용하는 간단한 예제입니다:

```php
$color = "파란색";

switch ($color) {
    case "빨간색":
        echo "색상은 빨간색입니다.";
        break;
    case "초록색":
        echo "색상은 초록색입니다.";
        break;
    default:
        echo "색상은 정의되지 않았습니다.";
}
```
위 예제에서 `$color`가 "빨간색"이나 "초록색"이 아닐 경우, "색상은 정의되지 않았습니다."라는 메시지가 출력됩니다.

### 복합 예제
여러 조건을 처리하는 예제:

```php
$fruit = "사과";

switch ($fruit) {
    case "바나나":
        echo "바나나를 선택했습니다.";
        break;
    case "귤":
        echo "귤을 선택했습니다.";
        break;
    default:
        echo "과일을 선택하지 않았습니다.";
}
```
이 예제에서도 `default`는 모든 다른 과일이 선택되지 않았을 때 실행됩니다.

## 설명
- **일치하는 case 없음**: `default` 블록은 switch 문에서 어떤 case도 일치하지 않을 때 실행됩니다. 모든 가능성을 고려하여 적절한 오류 처리를 제공하는 것이 좋습니다.
- **여러 개의 default 사용 금지**: 한 switch 문 내에서 `default` 블록은 하나만 존재해야 하며, 여러 개를 정의하면 오류가 발생합니다.
- **이해하기 쉬운 코드**: 코드의 가독성을 높이기 위해 `default`는 항상 마지막에 위치하는 것이 권장됩니다.

## 한 줄 요약
PHP의 'default'는 switch 문에서 조건이 맞지 않을 때 실행되는 기본 코드 블록을 정의하는 데 사용됩니다.