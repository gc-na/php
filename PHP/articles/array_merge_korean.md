<!--
Meta Description: # PHP array_merge 함수: 배열 병합의 모든 것 ## 개요 PHP의 `array_merge` 함수는 두 개 이상의 배열을 병합하여 하나의 배열로 만드는 기능을 제공합니다. 이 함수는 배열의 요소를 결합하여 새로운 배열을 생성하는 데 유용하며, 데이터 처리 ...
Meta Keywords: array_merge, 배열을, php, array1, array2
-->

# PHP array_merge 함수: 배열 병합의 모든 것

## 개요
PHP의 `array_merge` 함수는 두 개 이상의 배열을 병합하여 하나의 배열로 만드는 기능을 제공합니다. 이 함수는 배열의 요소를 결합하여 새로운 배열을 생성하는 데 유용하며, 데이터 처리 및 조작에 있어 필수적인 도구입니다.

## 문서
### 목적
`array_merge` 함수는 여러 배열을 병합하여 하나의 배열로 통합하는 데 사용됩니다. 배열의 키는 재정의되며, 키가 숫자인 경우에는 순서대로 병합됩니다.

### 사용법
```php
array array_merge(array ...$arrays)
```

- **매개변수**:
  - `...$arrays`: 병합할 배열들. 최소한 하나 이상의 배열이 필요합니다.

- **반환값**:
  - 병합된 새로운 배열을 반환합니다.

### 예제
1. **기본 사용법**
```php
$array1 = ["a" => "apple", "b" => "banana"];
$array2 = ["b" => "blueberry", "c" => "cherry"];
$result = array_merge($array1, $array2);

print_r($result);
/* 출력:
Array
(
    [a] => apple
    [b] => blueberry
    [c] => cherry
)
*/
```

2. **숫자 키 배열 병합**
```php
$array1 = [1, 2, 3];
$array2 = [4, 5, 6];
$result = array_merge($array1, $array2);

print_r($result);
/* 출력:
Array
(
    [0] => 1
    [1] => 2
    [2] => 3
    [3] => 4
    [4] => 5
    [5] => 6
)
*/
```

3. **비어 있는 배열 병합**
```php
$array1 = [];
$array2 = ["a" => "apple"];
$result = array_merge($array1, $array2);

print_r($result);
/* 출력:
Array
(
    [a] => apple
)
*/
```

## 설명
`array_merge` 함수를 사용할 때 몇 가지 주의할 점이 있습니다. 첫째, 배열의 키가 문자열일 경우, 같은 키가 있을 때 마지막 배열의 값으로 덮어쓰게 됩니다. 둘째, 배열의 키가 숫자인 경우에는 키가 재정의되지 않고 단순히 요소가 뒤에 추가됩니다.

### 일반적인 오류 및 유의사항
- 배열을 병합할 때, 같은 문자열 키가 있는 경우에는 기존 값이 덮어씌워지므로 주의해야 합니다.
- `array_merge`는 원본 배열을 변경하지 않고 새로운 배열을 반환하므로, 원본 배열이 필요한 경우 복사본을 만들어야 합니다.
- PHP 7.4 이상에서는 `array_merge`가 성능 문제로 인해 내부적으로 최적화되어 처리 속도가 개선되었습니다.

## 한 줄 요약
`array_merge` 함수는 여러 배열을 병합하여 하나의 새로운 배열을 생성하는 PHP의 유용한 도구입니다.