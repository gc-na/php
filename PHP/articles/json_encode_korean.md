<!--
Meta Description: # PHP의 json_encode: JSON으로 변환하는 방법 ## 요약 `json_encode`는 PHP에서 변수를 JSON 형식의 문자열로 변환하는 함수입니다. 이 함수를 사용하면 배열이나 객체를 쉽게 JSON으로 변환하여 웹 API와의 데이터 전송이나 저장이 용이...
Meta Keywords: json_encode, json, name, age, 데이터
-->

# PHP의 json_encode: JSON으로 변환하는 방법

## 요약
`json_encode`는 PHP에서 변수를 JSON 형식의 문자열로 변환하는 함수입니다. 이 함수를 사용하면 배열이나 객체를 쉽게 JSON으로 변환하여 웹 API와의 데이터 전송이나 저장이 용이해집니다.

## 문서화
`json_encode` 함수는 PHP의 내장 함수로, 주어진 값을 JSON 형식으로 인코딩합니다. 이 함수는 주로 데이터 교환 및 API 응답을 생성하는 데 사용됩니다. JSON은 경량의 데이터 형식으로, 다양한 플랫폼 간의 데이터 전송에 적합합니다.

### 사용법
```php
json_encode(mixed $value, int $options = 0, int $depth = 512): string|false
```
- **$value**: JSON으로 변환하고자 하는 값 (배열, 객체 등).
- **$options**: 인코딩 옵션으로, 여러 가지 플래그를 조합할 수 있습니다. 예: `JSON_PRETTY_PRINT`, `JSON_UNESCAPED_SLASHES` 등.
- **$depth**: 최대 깊이로, 기본값은 512입니다. 깊이가 이 값을 초과할 경우 `false`를 반환합니다.

### 반환값
성공할 경우 JSON 문자열을 반환하고, 실패할 경우 `false`를 반환합니다. 이때 오류는 `json_last_error` 함수를 통해 확인할 수 있습니다.

## 예제
기본적인 사용 예제는 다음과 같습니다.

### 배열 인코딩
```php
$data = array("name" => "홍길동", "age" => 30, "city" => "서울");
$json = json_encode($data);
echo $json; // {"name":"홍길동","age":30,"city":"서울"}
```

### 객체 인코딩
```php
class Person {
    public $name;
    public $age;
}

$person = new Person();
$person->name = "김철수";
$person->age = 25;

$json = json_encode($person);
echo $json; // {"name":"김철수","age":25}
```

### 옵션 사용
```php
$data = array("name" => "이영희", "age" => 28);
$json = json_encode($data, JSON_PRETTY_PRINT);
echo $json;
/*
출력:
{
    "name": "이영희",
    "age": 28
}
*/
```

## 설명
`json_encode`를 사용할 때 몇 가지 주의해야 할 점이 있습니다.

1. **지원되는 데이터 타입**: PHP의 스칼라 타입, 배열, 객체는 지원되지만, 자원(Resource)나 특정 객체 타입은 지원되지 않습니다.
2. **UTF-8 인코딩**: `json_encode`는 입력된 데이터가 UTF-8로 인코딩되어 있어야 합니다. 다른 인코딩의 문자열은 올바르게 인코딩되지 않을 수 있습니다.
3. **부정확한 인코딩**: 배열이나 객체의 속성이 `null`인 경우, 해당 속성은 JSON에서 생략됩니다.
4. **오류 처리**: `json_encode`가 실패할 경우, `json_last_error`와 `json_last_error_msg` 함수를 사용하여 오류를 진단할 수 있습니다.

## 한 줄 요약
`json_encode`는 PHP에서 배열 및 객체를 JSON 형식으로 변환하여 데이터 전송을 간편하게 하는 함수입니다.