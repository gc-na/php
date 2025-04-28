<!--
Meta Description: # PHP의 str_replace 함수: 문자열 대체의 모든 것 ## 개요 `str_replace` 함수는 PHP에서 문자열 내의 특정 문자열을 다른 문자열로 대체하는 데 사용됩니다. 이 함수는 문자열 조작을 간편하게 해주며, 다양한 상황에서 유용하게 활용됩니다. ##...
Meta Keywords: 문자열, str_replace, 함수는, 문자열을, php
-->

# PHP의 str_replace 함수: 문자열 대체의 모든 것

## 개요
`str_replace` 함수는 PHP에서 문자열 내의 특정 문자열을 다른 문자열로 대체하는 데 사용됩니다. 이 함수는 문자열 조작을 간편하게 해주며, 다양한 상황에서 유용하게 활용됩니다.

## 문서화
### 목적
`str_replace` 함수는 주어진 문자열에서 특정 부분 문자열을 찾아 다른 문자열로 대체하는 기능을 제공합니다. 이 함수는 대소문자를 구분하며, 여러 문자열을 동시에 대체할 수 있습니다.

### 사용법
```php
string str_replace(mixed $search, mixed $replace, mixed $subject[, int &$count])
```

- **$search**: 대체할 문자열 또는 문자열 배열.
- **$replace**: 대체할 문자열 또는 문자열 배열.
- **$subject**: 검색할 문자열 또는 문자열 배열.
- **$count** (선택적): 대체된 횟수를 저장할 변수.

### 반환값
대체된 문자열을 반환합니다. 만약 $subject가 배열인 경우, 대체된 문자열의 배열이 반환됩니다.

## 예제
### 기본 사용
```php
$text = "Hello, World!";
$newText = str_replace("World", "PHP", $text);
echo $newText; // 출력: Hello, PHP!
```

### 배열을 통한 대체
```php
$search = array("cat", "dog");
$replace = array("고양이", "개");
$text = "나는 고양이와 개를 좋아합니다.";
$newText = str_replace($search, $replace, $text);
echo $newText; // 출력: 나는 고양이와 개를 좋아합니다. (변경 없음)
```

### 대체 횟수 확인
```php
$text = "apple apple apple";
$count = 0;
$newText = str_replace("apple", "orange", $text, $count);
echo $newText; // 출력: orange orange orange
echo $count;   // 출력: 3
```

## 설명
`str_replace` 함수는 매우 유용하지만 몇 가지 주의할 점이 있습니다. 

- **대소문자 구분**: 기본적으로 대소문자를 구분하므로, 대체할 문자열의 대소문자가 정확히 일치해야 합니다.
- **배열 사용 시**: $search와 $replace는 배열로 함께 사용될 수 있으며, 둘의 길이는 같아야 합니다. 그렇지 않으면 예기치 않은 결과가 발생할 수 있습니다.
- **UTF-8 문자열**: `str_replace`는 UTF-8 문자열을 처리할 수 있지만, 복잡한 문자열 조작이 필요한 경우 `mb_str_replace`와 같은 다국어 문자열 대체 함수를 사용하는 것이 좋습니다.

## 한 줄 요약
`str_replace` 함수는 PHP에서 문자열 내 특정 부분 문자열을 다른 문자열로 대체하는 간편한 방법을 제공합니다.