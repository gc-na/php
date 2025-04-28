<!--
Meta Description: # PHP의 require: 필수 파일 포함하기 ## 개요 PHP에서 `require`는 다른 PHP 파일을 현재 스크립트에 포함시키는 데 사용되는 명령어로, 코드의 재사용성과 구조화를 돕습니다. `require`는 포함된 파일이 존재하지 않거나 읽을 수 없을 경우 치...
Meta Keywords: php, require, 파일이, 경로를, 파일을
-->

# PHP의 require: 필수 파일 포함하기

## 개요
PHP에서 `require`는 다른 PHP 파일을 현재 스크립트에 포함시키는 데 사용되는 명령어로, 코드의 재사용성과 구조화를 돕습니다. `require`는 포함된 파일이 존재하지 않거나 읽을 수 없을 경우 치명적인 오류를 발생시킵니다.

## 문서화
`require` 명령어는 PHP 스크립트에서 다른 파일의 내용을 삽입하는 데 사용됩니다. 이 명령어는 주로 공통적으로 사용되는 함수, 클래스, 또는 설정 파일을 포함할 때 유용합니다. `require`를 사용하면 파일이 한 번 포함되고, 그 이후에 다시 포함되지 않도록 보장됩니다.

### 용법
```php
require '파일경로.php';
```

- **파일경로**: 포함할 PHP 파일의 경로입니다. 절대 경로 또는 상대 경로를 사용할 수 있습니다.

### 세부사항
- `require`는 스크립트 실행 중 파일이 없으면 오류를 발생시키며, 스크립트 실행이 중단됩니다.
- `require_once`와 비교할 수 있는데, 후자는 파일이 이미 포함되었을 경우 다시 포함되지 않도록 보장합니다.
- `require`는 PHP의 기본 기능으로, 누구나 쉽게 사용할 수 있습니다.

## 예제
### 기본 사용 예제
```php
// config.php
<?php
$database_host = 'localhost';
$database_user = 'root';
$database_password = '';
?>

// main.php
<?php
require 'config.php';
echo $database_host; // 출력: localhost
?>
```

### 오류 발생 예제
```php
// main.php
<?php
require 'nonexistent.php'; // 'nonexistent.php'가 없으므로 오류 발생
?>
```

## 설명
`require`를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:
- 포함할 파일의 경로가 정확한지 확인해야 합니다. 잘못된 경로를 사용하면 치명적인 오류가 발생합니다.
- `require`는 파일을 한 번만 포함하므로, 중복 포함에 주의해야 합니다. 중복 포함을 피하려면 `require_once`를 사용하는 것이 좋습니다.
- 파일의 경로를 지정할 때 절대 경로를 사용하는 것이 좋습니다. 상대 경로를 사용할 경우, 실행 환경에 따라 다르게 작동할 수 있습니다.

## 한줄 요약
`require`는 PHP에서 필수 파일을 포함시키는 명령어로, 포함된 파일이 없으면 오류를 발생시킵니다.