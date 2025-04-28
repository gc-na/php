<!--
Meta Description: # PHP의 json_decode 함수: JSON 데이터를 PHP 배열로 변환하기 ## 개요 `json_decode`는 JSON 형식의 문자열을 PHP에서 사용할 수 있는 배열 또는 객체로 변환하는 함수입니다. JSON(JavaScript Object Notation)...
Meta Keywords: json, json_decode, php, 있습니다, 사용할
-->

# PHP의 json_decode 함수: JSON 데이터를 PHP 배열로 변환하기

## 개요
`json_decode`는 JSON 형식의 문자열을 PHP에서 사용할 수 있는 배열 또는 객체로 변환하는 함수입니다. JSON(JavaScript Object Notation)은 데이터를 교환하는 데 널리 사용되는 경량 형식으로, PHP에서 JSON 데이터를 다룰 때 필수적인 기능입니다.

## 문서화

### 목적
`json_decode` 함수는 JSON 문자열을 PHP의 데이터 구조로 변환하여, 프로그래머가 JSON 데이터를 쉽게 조작하고 활용할 수 있도록 돕습니다.

### 사용법
```php
mixed json_decode(string $json, bool $assoc = false, int $depth = 512, int $options = 0)
```

### 매개변수
- **$json**: 변환할 JSON 문자열입니다.
- **$assoc**: (선택 사항) `true`로 설정하면 연관 배열로 반환하고, `false`로 설정하면 객체로 반환합니다. 기본값은 `false`입니다.
- **$depth**: (선택 사항) JSON 구문 분석의 최대 깊이를 설정합니다. 기본값은 512입니다.
- **$options**: (선택 사항) JSON 구문 분석에 사용할 추가 옵션을 설정합니다. 기본값은 0입니다.

### 반환값
- 변환에 성공하면 PHP 배열 또는 객체를 반환합니다.
- JSON 문자열이 유효하지 않으면 `null`을 반환하며, 이 경우 `json_last_error()` 함수를 사용하여 오류를 확인할 수 있습니다.

## 예제

### 기본 사용 예제
```php
$json = '{"name": "홍길동", "age": 30, "city": "서울"}';
$data = json_decode($json);
echo $data->name; // 출력: 홍길동
```

### 연관 배열로 변환
```php
$json = '{"name": "홍길동", "age": 30, "city": "서울"}';
$data = json_decode($json, true);
echo $data['name']; // 출력: 홍길동
```

## 설명
`json_decode`를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:

- **유효성 검사**: JSON 문자열이 유효하지 않으면 `null`이 반환됩니다. 이 경우, `json_last_error()`를 호출하여 오류를 확인할 수 있습니다. 예를 들어:
  ```php
  $json = '{"name": "홍길동", "age": 30, "city": "서울"'; // 잘못된 JSON
  $data = json_decode($json);
  
  if (json_last_error() !== JSON_ERROR_NONE) {
      echo 'JSON 오류: ' . json_last_error_msg(); // 오류 메시지 출력
  }
  ```

- **데이터 타입**: JSON에서 정수, 문자열, 불리언, 배열, 객체 등을 지원하며, PHP 배열과 객체로 변환할 수 있습니다. JSON의 `null` 값은 PHP의 `null`로 변환됩니다.

- **옵션 파라미터**: JSON 구문 분석에 사용할 추가 옵션을 지정할 수 있습니다. 예를 들어, `JSON_BIGINT_AS_STRING` 옵션을 사용하면 큰 정수를 문자열로 변환할 수 있습니다.

## 한 줄 요약
`json_decode` 함수는 JSON 문자열을 PHP에서 사용할 수 있는 배열 또는 객체로 변환하는 유용한 기능입니다.